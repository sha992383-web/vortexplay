<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY ☁️</title>
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:Tahoma,sans-serif;min-height:100vh;
    background:linear-gradient(135deg,#0F0520,#2A1050,#1A0A3C);color:#fff;padding:15px}
.container{max-width:650px;margin:0 auto}
h1{text-align:center;color:#FFD700;margin:20px 0;text-shadow:0 0 15px #FFD700}
.card{background:rgba(30,15,60,.85);border-radius:16px;padding:20px;margin-bottom:20px;
    border:1px solid rgba(255,215,0,.2);backdrop-filter:blur(10px)}
input,textarea{width:100%;padding:12px;border-radius:10px;border:1px solid rgba(255,215,0,.3);
    background:rgba(0,0,0,.4);color:#fff;font-size:14px;margin-bottom:10px}
button{width:100%;padding:13px;border-radius:10px;border:none;font-size:16px;font-weight:bold;
    background:linear-gradient(90deg,#FFD700,#FF6B00);color:#000;cursor:pointer;margin-top:5px}
button:active{transform:scale(.97)}
button.small{width:auto;padding:8px 15px;font-size:13px;background:rgba(0,217,255,.2);color:#00D9FF;
    border:1px solid #00D9FF}
.status{text-align:center;padding:10px;border-radius:8px;margin:10px 0;font-size:13px}
.ok{background:rgba(0,255,136,.15);color:#00FF88}
.wait{background:rgba(255,200,0,.15);color:#ffcc00}
.err{background:rgba(255,51,102,.15);color:#FF3366}
.msg{padding:15px;border-bottom:1px dashed rgba(255,255,255,.1)}
.msg:last-child{border-bottom:none}
.name{color:#FFD700;font-weight:bold;margin-bottom:5px}
.time{color:#888;font-size:11px;margin-bottom:8px}
.text{line-height:1.7;white-space:pre-wrap}
.empty{text-align:center;padding:40px;color:#777}
.controls{display:flex;gap:8px;margin-top:10px;flex-wrap:wrap}
.file-label{display:inline-block;padding:10px 15px;background:rgba(0,217,255,.2);
    border-radius:8px;color:#00D9FF;cursor:pointer;font-size:13px;margin:10px 0}
.hidden{display:none}
</style>
</head>
<body>
<div class="container">
<h1>👑 VORTEXPLAY ☁️</h1>

<div class="card">
<input type="text" id="uName" placeholder="نام شما" maxlength="20">
<textarea id="uMsg" placeholder="پیام خود را بنویسید..."></textarea>
<label class="file-label">📁 انتخاب فایل<input type="file" id="uFile" class="hidden"></label>
<button onclick="send()">📤 ارسال پیام</button>
<div id="stat" class="status wait">⏳ در حال اتصال...</div>
<div class="controls">
<button class="small" onclick="getAll()">🔄 بروزرسانی دستی</button>
<span style="color:#666;font-size:12px">🔄 هر ۵ ثانیه خودکار بروزرسانی می‌شود</span>
</div>
</div>

<div class="card"><div id="list"></div></div>
</div>

<script>
// ==============================================
// ✅ همه چیز از قبل تنظیم شده! کاری نکن
const BIN_ID = '6ab5a0c1ac6210605af2700e';
const MASTER_KEY = '$2a$10$UjKZraBn9B.p9tfKZ6xzzuBs1uGDggLoZbjCdt9T9jVDor9.KGK56';
// ==============================================

const API = 'https://api.jsonbin.io/v3/b/' + BIN_ID;
const HEAD = {'X-Master-Key': MASTER_KEY, 'Content-Type':'application/json'};
let lastId = '';

function showStat(txt, t='wait'){
  const el = document.getElementById('stat');
  el.className = `status ${t}`;
  el.textContent = txt;
}

async function getAll(){
  try{
    const res = await fetch(API + '/latest?t=' + Date.now(), {
      headers: HEAD, cache:'no-store'
    });
    if(!res.ok) throw new Error('خطا');
    const data = await res.json();
    const msgs = data.record.messages || [];
    
    const currId = msgs.length ? msgs[0].id : 'empty';
    if(currId !== lastId){
      lastId = currId;
      render(msgs);
      showStat(`✅ متصل — ${msgs.length} پیام`,'ok');
    }
  }catch(e){
    showStat('❌ خطا در دریافت: ' + e.message,'err');
  }
}

async function send(){
  const name = document.getElementById('uName').value.trim() || 'ناشناس';
  const text = document.getElementById('uMsg').value.trim();
  const file = document.getElementById('uFile').files[0];
  
  if(!text && !file){ alert('چیزی بنویس یا فایل انتخاب کن!'); return; }
  
  showStat('⏳ در حال ارسال...');
  
  let fileInfo = null;
  if(file){
    fileInfo = {name:file.name, size:(file.size/1024).toFixed(1)+'KB'};
  }
  
  const old = await fetch(API + '/latest?t=' + Date.now(), {headers:HEAD, cache:'no-store'});
  const oldData = await old.json();
  const all = oldData.record.messages || [];
  
  all.unshift({
    id: Date.now(),
    name: name,
    text: text,
    file: fileInfo,
    time: new Date().toLocaleString('fa-IR')
  });
  
  await fetch(API, {
    method:'PUT',
    headers: HEAD,
    body: JSON.stringify({messages: all})
  });
  
  showStat('✅ ارسال شد!','ok');
  document.getElementById('uMsg').value = '';
  document.getElementById('uFile').value = '';
  lastId = all[0].id;
  render(all);
}

function render(msgs){
  const el = document.getElementById('list');
  if(!msgs.length){
    el.innerHTML = '<div class="empty">هنوز پیامی نیست ✍️ اولین پیام را شما بنویسید!</div>';
    return;
  }
  el.innerHTML = msgs.map(m => `
    <div class="msg">
      <div class="name">👤 ${escape(m.name)}</div>
      <div class="time">${m.time}</div>
      ${m.text?`<div class="text">${escape(m.text)}</div>`:''}
      ${m.file?`<div style="margin-top:8px;padding:8px;background:rgba(0,217,255,.1);border-radius:6px">📁 ${escape(m.file.name)} (${m.file.size})</div>`:''}
    </div>
  `).join('');
}

function escape(t){
  const d=document.createElement('div');d.textContent=t;return d.innerHTML;
}

setInterval(getAll, 5000);
getAll();
</script>
</body>
</html>
