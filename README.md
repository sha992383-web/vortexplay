<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>تابلو عمومی VORTEXPLAY 📢</title>
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:Tahoma,sans-serif;min-height:100vh;
    background:linear-gradient(160deg,#0d0618,#2d1b4e,#1a0b2e);
    color:#f5e6a3;padding:20px}
.container{max-width:600px;margin:0 auto}
h1{text-align:center;color:#ffd700;margin:25px 0;text-shadow:0 0 15px #ffd700}
.card{background:rgba(26,11,46,.8);border:2px solid rgba(255,215,0,.4);
    border-radius:16px;padding:20px;margin-bottom:20px;backdrop-filter:blur(10px)}
.send-box{position:sticky;top:15px;z-index:10;background:linear-gradient(160deg,#1a0b2e,#2d1b4e);
    box-shadow:0 0 25px rgba(255,215,0,.25)}
textarea{width:100%;height:100px;padding:12px;border-radius:10px;
    border:2px solid rgba(255,215,0,.3);background:rgba(13,6,24,.7);
    color:#f5e6a3;font-size:15px;resize:none;margin-bottom:10px}
button{width:100%;padding:12px;border-radius:10px;border:none;
    background:linear-gradient(90deg,#ffd700,#b8860b);color:#1a0b2e;
    font-weight:bold;font-size:16px;cursor:pointer;transition:.2s}
button:active{transform:scale(.97)}
button.danger{background:linear-gradient(90deg,#ff2244,#ff4466);color:#fff}
.msg{border-bottom:1px dashed rgba(255,215,0,.25);padding:15px 0}
.msg:last-child{border-bottom:none}
.msg-text{font-size:15px;line-height:1.8;margin-bottom:8px;white-space:pre-wrap}
.msg-time{font-size:12px;color:#d4af37;opacity:.7}
.msg-author{font-size:13px;color:#ffd700;margin-bottom:5px}
.empty{text-align:center;padding:40px 20px;color:#d4af37}
.pin{border-left:3px solid #ffd700;padding-left:12px;background:rgba(255,215,0,.08);border-radius:0 8px 8px 0}
.controls{display:flex;gap:10px;margin-top:10px}
.controls button{flex:1;font-size:13px;padding:8px}
.name-input{padding:10px;border-radius:8px;border:2px solid rgba(255,215,0,.3);
    background:rgba(13,6,24,.7);color:#f5e6a3;font-size:14px;margin-bottom:12px;width:100%}
.sync-info{text-align:center;font-size:12px;color:#d4af37;margin:10px 0;opacity:.7}
</style>
</head>
<body>
<div class="container">
<h1>📢 تابلو عمومی پیام‌ها</h1>

<div class="card send-box">
<input type="text" id="userName" class="name-input" placeholder="نام شما" maxlength="20">
<textarea id="msgInput" placeholder="پیام خود را بنویسید..."></textarea>
<button onclick="sendMsg()">📤 ارسال پیام</button>
<div class="sync-info" id="syncInfo">💡 پیام‌ها در همین دستگاه ذخیره می‌شوند</div>
<div class="controls">
<button onclick="exportMsgs()">📤 خروجی پیام‌ها</button>
<button onclick="clearAll()" class="danger">🗑 پاک کردن همه</button>
</div>
<input type="file" id="importFile" accept=".json" style="display:none" onchange="importMsgs(this)">
<button onclick="document.getElementById('importFile').click()" style="margin-top:8px">📥 وارد کردن پیام‌ها</button>
</div>

<div class="card">
<div id="msgsList"></div>
</div>
</div>

<script>
const STORAGE_KEY = 'vortex_board';
let msgs = [];

function loadMsgs(){
  const saved = localStorage.getItem(STORAGE_KEY);
  if(saved) msgs = JSON.parse(saved);
  renderMsgs();
}

function saveMsgs(){
  localStorage.setItem(STORAGE_KEY, JSON.stringify(msgs));
}

function sendMsg(){
  const name = document.getElementById('userName').value.trim() || 'ناشناس';
  const text = document.getElementById('msgInput').value.trim();
  if(!text){ alert('لطفاً پیام را بنویسید!'); return; }
  
  msgs.unshift({
    id: Date.now(),
    name: name,
    text: text,
    time: new Date().toLocaleString('fa-IR'),
    pinned: false
  });
  
  saveMsgs();
  renderMsgs();
  document.getElementById('msgInput').value = '';
}

function renderMsgs(){
  const list = document.getElementById('msgsList');
  if(!msgs.length){
    list.innerHTML = '<div class="empty">هنوز پیامی ارسال نشده<br>اولین پیام را شما بنویسید! ✍️</div>';
    return;
  }
  
  list.innerHTML = msgs.map(m => `
    <div class="msg ${m.pinned?'pin':''}">
      <div class="msg-author">${m.pinned?'📌 ':''}${escapeHtml(m.name)}</div>
      <div class="msg-text">${escapeHtml(m.text)}</div>
      <div class="msg-time">${m.time}</div>
    </div>
  `).join('');
}

function escapeHtml(text){
  const div = document.createElement('div');
  div.textContent = text;
  return div.innerHTML;
}

function exportMsgs(){
  const blob = new Blob([JSON.stringify(msgs,null,2)], {type:'application/json'});
  const a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = 'board-messages.json';
  a.click();
  alert('✅ پیام‌ها ذخیره شدند! فایل را به بقیه بدهید تا وارد کنند');
}

function importMsgs(input){
  const file = input.files[0];
  if(!file) return;
  if(!confirm('پیام‌های فعلی حذف و جایگزین شوند؟')) return;
  
  const reader = new FileReader();
  reader.onload = e => {
    try{
      msgs = JSON.parse(e.target.result);
      saveMsgs();
      renderMsgs();
      alert('✅ پیام‌ها بارگذاری شدند!');
    }catch{
      alert('❌ فایل نامعتبر است');
    }
  };
  reader.readAsText(file);
  input.value = '';
}

function clearAll(){
  if(!confirm('مطمئنی همه پیام‌ها پاک شوند؟ بازگشت ندارد!')) return;
  msgs = [];
  saveMsgs();
  renderMsgs();
}

loadMsgs();
</script>
</body>
</html>
