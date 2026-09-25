<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXSTORE 👑</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Tahoma,sans-serif}
:root{--gold:#FFD700;--orange:#FF6B00;--dark:#0F0F1A;--purple:#7B2CFF;--cyan:#00D4FF}
body{background:linear-gradient(135deg,#0F0F1A,#1A1A3A);min-height:100vh;color:#fff;padding:15px}
.container{max-width:700px;margin:0 auto}
.header{text-align:center;padding:30px 0;border-bottom:2px solid var(--gold)}
.logo{font-size:2.2rem;font-weight:bold;background:linear-gradient(90deg,var(--gold),var(--orange));-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.nav{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin:25px 0}
.nav-btn{background:linear-gradient(90deg,var(--purple),var(--cyan));border:none;padding:12px 20px;border-radius:10px;color:#fff;font-size:15px;cursor:pointer;transition:.3s}
.nav-btn:hover{transform:scale(1.05);box-shadow:0 0 12px var(--cyan)}
.nav-btn.active{box-shadow:0 0 15px var(--gold)}
.box{background:rgba(255,255,255,.05);border-radius:15px;padding:20px;border:1px solid rgba(255,215,0,.3);min-height:300px}
.msg{background:rgba(255,255,255,.08);padding:15px;border-radius:10px;margin:10px 0;border-right:3px solid var(--gold)}
.msg-text{line-height:1.8;margin-bottom:8px}
.msg-time{font-size:12px;color:#777}
.empty{text-align:center;padding:40px;color:#666}
.admin-btn{position:fixed;top:15px;left:15px;width:48px;height:48px;border-radius:50%;border:none;background:linear-gradient(90deg,var(--gold),var(--orange));font-size:20px;cursor:pointer;z-index:999}
.modal{position:fixed;inset:0;background:rgba(0,0,0,.92);display:none;align-items:center;justify-content:center;padding:20px;z-index:1000}
.modal.show{display:flex}
.modal-box{background:#1A1A3A;border-radius:15px;padding:25px;border:2px solid var(--gold);width:100%;max-width:450px}
input,textarea,select{width:100%;padding:12px;border-radius:8px;border:1px solid #444;background:#0F0F1A;color:#fff;margin:8px 0;font-size:15px}
.btn{width:100%;padding:14px;border-radius:10px;border:none;font-size:16px;font-weight:bold;cursor:pointer;margin-top:8px}
.btn-primary{background:linear-gradient(90deg,var(--gold),var(--orange));color:#000}
.btn-small{width:auto;padding:10px 18px;background:rgba(0,212,255,.15);color:var(--cyan);border:1px solid rgba(0,212,255,.3)}
.btn-danger{background:rgba(255,68,68,.2);color:#FF4444;border:1px solid rgba(255,68,68,.3)}
.hidden{display:none}
a{color:var(--cyan);text-decoration:none}
</style>
</head>
<body>

<button class="admin-btn" onclick="openPanel()">⚙️</button>

<div class="container">
  <div class="header">
    <h1 class="logo">👑 VORTEXSTORE</h1>
    <p style="color:#888;margin-top:8px">پایگاه گیمینگ و دانلود</p>
  </div>

  <div class="nav">
    <button class="nav-btn active" data-cat="payload">📦 پیلود</button>
    <button class="nav-btn" data-cat="backup">💾 بکاپ</button>
    <button class="nav-btn" data-cat="game">🎮 بازی</button>
  </div>

  <div class="box" id="msgs">
    <p class="empty">در حال بارگذاری...</p>
  </div>
</div>

<div class="modal" id="panel">
  <div class="modal-box">
    <h3 style="color:var(--gold);text-align:center;margin-bottom:15px">🔐 پنل مدیریت</h3>
    <input type="password" id="pass" placeholder="رمز ۳۲ رقمی">
    <button class="btn btn-primary" onclick="checkPass()">ورود</button>
    <button class="btn btn-small" style="width:100%;margin-top:8px" onclick="closePanel()">بستن</button>
    
    <div id="adminContent" class="hidden">
      <select id="cat">
        <option value="payload">پیلود</option>
        <option value="backup">بکاپ</option>
        <option value="game">بازی</option>
      </select>
      <textarea id="msgText" rows="4" placeholder="متن پیام..."></textarea>
      <input type="text" id="msgLink" placeholder="لینک دانلود (اختیاری)">
      <button class="btn btn-primary" onclick="sendMsg()">✅ ارسال پیام</button>
      <button class="btn btn-danger btn-small" style="width:100%;margin-top:8px" onclick="closePanel()">بستن</button>
    </div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
<script>
// ========== مقادیر شما ==========
const SUPABASE_URL = "https://wdtaeumtkauoewaghpxb.supabase.co";
const SUPABASE_KEY = "sb_publishable_lHHour5qR6c5kVOiuptaig_Cuxz-ON8";
const ADMIN_PASS = "VORTEX2026abc123XYZ789!@#$%^&*()";
// ===============================

const { createClient } = supabase;
const supabase = createClient(SUPABASE_URL, SUPABASE_KEY);

let currentCat = 'payload';

async function loadMessages(){
  const {data, error} = await supabase
    .from('messages')
    .select('*')
    .eq('category', currentCat)
    .order('created_at', {ascending: false});
  
  const box = document.getElementById('msgs');
  if(!data || data.length === 0){
    box.innerHTML = '<p class="empty">هنوز پیامی ارسال نشده ✍️ اولین پیام را شما بنویسید!</p>';
    return;
  }
  box.innerHTML = data.map(m => `
    <div class="msg">
      <div class="msg-text">${m.text}${m.link ? `<br><br>🔗 <a href="${m.link}" target="_blank">دانلود</a>` : ''}</div>
      <div class="msg-time">${new Date(m.created_at).toLocaleString('fa-IR')}</div>
    </div>
  `).join('');
}

async function sendMsg(){
  const text = document.getElementById('msgText').value.trim();
  const link = document.getElementById('msgLink').value.trim();
  if(!text) return alert('متن پیام را بنویسید!');

  const {error} = await supabase.from('messages').insert({
    category: document.getElementById('cat').value,
    text: text,
    link: link || null
  });

  if(error) alert('❌ خطا: ' + error.message);
  else {
    alert('✅ پیام ارسال شد! همه می‌بینند');
    document.getElementById('msgText').value = '';
    document.getElementById('msgLink').value = '';
    loadMessages();
  }
}

document.querySelectorAll('.nav-btn[data-cat]').forEach(btn => {
  btn.onclick = () => {
    document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    currentCat = btn.dataset.cat;
    loadMessages();
  };
});

function openPanel(){
  document.getElementById('panel').classList.add('show');
  document.getElementById('pass').value = '';
  document.getElementById('adminContent').classList.add('hidden');
}

function closePanel(){
  document.getElementById('panel').classList.remove('show');
}

function checkPass(){
  if(document.getElementById('pass').value === ADMIN_PASS){
    document.getElementById('adminContent').classList.remove('hidden');
  } else {
    alert('❌ رمز اشتباه است!');
  }
}

loadMessages();

supabase.channel('public:messages').on(
  'postgres_changes',
  { event: 'INSERT', schema: 'public', table: 'messages' },
  () => loadMessages()
).subscribe();
</script>
</body>CREATE TABLE messages (
  id BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  category TEXT NOT NULL,
  text TEXT NOT NULL,
  link TEXT,
  created_at TIMESTAMP DEFAULT now()
);

</html>
