<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY ☁️ تابلو ابری</title>
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }
:root {
  --gold: #FFD700;
  --orange: #FF6B00;
  --dark: #0F0520;
  --card: rgba(30, 15, 60, 0.85);
  --accent: #00D9FF;
  --success: #00FF88;
  --error: #FF3366;
}
body {
  font-family: Tahoma, sans-serif;
  min-height: 100vh;
  background: linear-gradient(135deg, #0F0520 0%, #2A1050 50%, #1A0A3C 100%);
  color: #fff;
  padding: 15px;
}
.container { max-width: 650px; margin: 0 auto; }
.header {
  text-align: center;
  padding: 25px 15px;
  margin-bottom: 20px;
  border-bottom: 2px solid transparent;
  border-image: linear-gradient(90deg, transparent, var(--gold), var(--orange), transparent) 1;
}
.logo {
  font-size: 28px;
  font-weight: bold;
  background: linear-gradient(90deg, var(--gold), var(--orange));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.subtitle { color: #aaa; font-size: 13px; margin-top: 5px; }
.card {
  background: var(--card);
  border-radius: 16px;
  padding: 20px;
  margin-bottom: 20px;
  border: 1px solid rgba(255, 215, 0, 0.2);
  box-shadow: 0 0 20px rgba(0, 217, 255, 0.1);
  backdrop-filter: blur(10px);
}
.send-box { position: sticky; top: 10px; z-index: 100; }
.input {
  width: 100%;
  padding: 12px 15px;
  border-radius: 10px;
  border: 1px solid rgba(255, 215, 0, 0.3);
  background: rgba(0, 0, 0, 0.4);
  color: #fff;
  font-size: 14px;
  margin-bottom: 10px;
  outline: none;
}
.input:focus { border-color: var(--gold); box-shadow: 0 0 10px rgba(255, 215, 0, 0.3); }
textarea.input { min-height: 100px; resize: vertical; }
.btn {
  width: 100%;
  padding: 13px;
  border-radius: 10px;
  border: none;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s;
  margin-top: 5px;
}
.btn-primary {
  background: linear-gradient(90deg, var(--gold), var(--orange));
  color: #000;
}
.btn-primary:active { transform: scale(0.97); }
.btn-secondary {
  background: rgba(0, 217, 255, 0.2);
  color: var(--accent);
  border: 1px solid var(--accent);
}
.btn-danger {
  background: rgba(255, 51, 102, 0.2);
  color: var(--error);
  border: 1px solid var(--error);
}
.btn-small { width: auto; padding: 8px 15px; font-size: 13px; }
.status {
  text-align: center;
  padding: 8px 12px;
  border-radius: 8px;
  font-size: 13px;
  margin-top: 12px;
}
.status.ok { background: rgba(0, 255, 136, 0.15); color: var(--success); }
.status.wait { background: rgba(255, 200, 0, 0.15); color: #ffcc00; }
.status.err { background: rgba(255, 51, 102, 0.15); color: var(--error); }
.msg {
  padding: 15px;
  border-bottom: 1px dashed rgba(255, 255, 255, 0.1);
  animation: fadeIn 0.3s ease;
}
@keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
.msg:last-child { border-bottom: none; }
.msg-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 8px;
}
.msg-author { color: var(--gold); font-weight: bold; font-size: 14px; }
.msg-time { color: #888; font-size: 11px; }
.msg-text { line-height: 1.7; font-size: 15px; white-space: pre-wrap; word-break: break-word; }
.empty { text-align: center; padding: 40px 20px; color: #777; }
.controls { display: flex; gap: 8px; margin-top: 10px; flex-wrap: wrap; }
.file-label {
  display: inline-block;
  padding: 10px 15px;
  background: rgba(0, 217, 255, 0.2);
  border-radius: 8px;
  color: var(--accent);
  cursor: pointer;
  font-size: 13px;
  margin-bottom: 10px;
}
.file-name { font-size: 12px; color: #aaa; margin-left: 8px; }
.hidden { display: none; }
.panel-toggle {
  position: fixed;
  top: 15px;
  left: 15px;
  background: linear-gradient(90deg, var(--gold), var(--orange));
  border: none;
  border-radius: 50%;
  width: 45px;
  height: 45px;
  font-size: 20px;
  cursor: pointer;
  z-index: 200;
  box-shadow: 0 0 15px rgba(255, 215, 0, 0.4);
}
.admin-panel {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  z-index: 300;
  display: none;
  align-items: center;
  justify-content: center;
  padding: 20px;
}
.admin-panel.show { display: flex; }
.admin-box {
  background: var(--card);
  border-radius: 16px;
  padding: 25px;
  border: 2px solid var(--gold);
  max-width: 400px;
  width: 100%;
}
.admin-title { color: var(--gold); margin-bottom: 20px; text-align: center; font-size: 20px; }
</style>
</head>
<body>

<button class="panel-toggle" onclick="togglePanel()">⚙️</button>

<div class="admin-panel" id="adminPanel">
  <div class="admin-box">
    <h2 class="admin-title">🔐 پنل مدیریت</h2>
    <input type="password" id="adminPassInput" class="input" placeholder="رمز مدیریت">
    <button class="btn btn-primary" onclick="checkAdmin()">ورود</button>
    <button class="btn btn-secondary btn-small" style="margin-top:10px" onclick="closePanel()">بستن</button>
    <div id="adminActions" class="hidden" style="margin-top:20px">
      <p style="color:#00FF88; margin-bottom:15px">✅ وارد شدید</p>
      <button class="btn btn-danger" onclick="clearAllMsgs()">حذف همه پیام‌ها</button>
    </div>
  </div>
</div>

<div class="container">
  <div class="header">
    <h1 class="logo">VORTEXPLAY</h1>
    <p class="subtitle">تابلو ابری پیام‌ها ☁️</p>
  </div>

  <div class="card send-box">
    <input type="text" id="userName" class="input" placeholder="نام شما" maxlength="20">
    <textarea id="msgInput" class="input" placeholder="پیام خود را بنویسید..."></textarea>
    
    <label class="file-label">
      📁 انتخاب فایل
      <input type="file" id="fileInput" class="hidden" onchange="showFileName()">
    </label>
    <span id="fileName" class="file-name"></span>
    
    <button class="btn btn-primary" onclick="sendMsg()">📤 ارسال پیام</button>
    <div id="status" class="status wait">⏳ در حال اتصال...</div>
    <div class="controls">
      <button class="btn btn-secondary btn-small" onclick="loadMsgs()">🔄 بروزرسانی</button>
      <span style="color:#666; font-size:12px; margin-left:auto">هر ۵ ثانیه خودکار بروزرسانی</span>
    </div>
  </div>

  <div class="card">
    <div id="msgsList"></div>
  </div>
</div>

<script>
// ==================================================
const JSONBIN_ID = '6ab59e4aac6210605af26b01';
const JSONBIN_KEY = '$2a$10$UjKZraBn9B.p9tfKZ6xzzuBs1uGDggLoZbjCdt9T9jVDor9.KGK56';
const ADMIN_PASS = 'VORTEX-992383-SHAHRIAR-2026';
// ==================================================

const API_URL = `https://api.jsonbin.io/v3/b/${JSONBIN_ID}`;
let msgs = [];
let lastSeenHash = '';
let isFirstLoad = true;

function showFileName() {
  const input = document.getElementById('fileInput');
  const name = document.getElementById('fileName');
  name.textContent = input.files.length > 0 ? '✅ ' + input.files[0].name : '';
}

function showStatus(text, type='wait') {
  const s = document.getElementById('status');
  s.className = `status ${type}`;
  s.textContent = text;
}

function getHash(arr) {
  if (!arr.length) return 'empty';
  return arr.map(m => m.id).join('|');
}

async function loadMsgs() {
  try {
    const res = await fetch(API_URL + '/latest?t=' + Date.now(), {
      headers: { 
        'X-Master-Key': JSONBIN_KEY,
        'Cache-Control': 'no-cache'
      },
      cache: 'no-store'
    });
    
    if (res.ok) {
      const data = await res.json();
      const newMsgs = data.record.messages || [];
      const newHash = getHash(newMsgs);
      
      if (newHash !== lastSeenHash) {
        msgs = newMsgs;
        lastSeenHash = newHash;
        renderMsgs();
        if (!isFirstLoad) {
          showStatus('✅ پیام جدید دریافت شد!', 'ok');
        }
      }
      
      showStatus(`✅ متصل — ${msgs.length} پیام`, 'ok');
      isFirstLoad = false;
    } else {
      showStatus('❌ خطا در دریافت', 'err');
    }
  } catch(e) {
    showStatus('❌ خطای شبکه', 'err');
  }
}

async function saveToCloud() {
  try {
    await fetch(API_URL, {
      method: 'PUT',
      headers: {
        'Content-Type': 'application/json',
        'X-Master-Key': JSONBIN_KEY
      },
      body: JSON.stringify({ messages: msgs, updated: new Date().toISOString() })
    });
    return true;
  } catch(e) {
    showStatus('❌ خطا در ذخیره', 'err');
    return false;
  }
}

async function sendMsg() {
  const name = document.getElementById('userName').value.trim() || 'ناشناس';
  const text = document.getElementById('msgInput').value.trim();
  const fileInput = document.getElementById('fileInput');
  
  if (!text && !fileInput.files.length) {
    alert('لطفاً پیام یا فایل را وارد کنید!');
    return;
  }
  
  showStatus('⏳ در حال ارسال...', 'wait');
  
  let fileInfo = null;
  if (fileInput.files.length > 0) {
    const file = fileInput.files[0];
    fileInfo = {
      name: file.name,
      size: (file.size / 1024).toFixed(1) + ' KB',
      type: file.type
    };
  }
  
  msgs.unshift({
    id: Date.now(),
    name: name,
    text: text,
    file: fileInfo,
    time: new Date().toLocaleString('fa-IR')
  });
  
  if (await saveToCloud()) {
    showStatus('✅ پیام ارسال شد!', 'ok');
    lastSeenHash = getHash(msgs);
    document.getElementById('msgInput').value = '';
    document.getElementById('fileInput').value = '';
    document.getElementById('fileName').textContent = '';
    renderMsgs();
  }
}

function renderMsgs() {
  const list = document.getElementById('msgsList');
  if (!msgs.length) {
    list.innerHTML = '<div class="empty">هنوز پیامی نیست<br>اولین پیام را شما بنویسید! ✍️</div>';
    return;
  }
  
  list.innerHTML = msgs.map(m => `
    <div class="msg">
      <div class="msg-header">
        <span class="msg-author">👤 ${escapeHtml(m.name)}</span>
        <span class="msg-time">${m.time}</span>
      </div>
      ${m.text ? `<div class="msg-text">${escapeHtml(m.text)}</div>` : ''}
      ${m.file ? `
        <div class="msg-file" style="margin-top:10px; padding:10px; background:rgba(0,217,255,0.1); border-radius:8px; border-left:3px solid #00D9FF">
          📁 <strong>${escapeHtml(m.file.name)}</strong><br>
          <span style="font-size:12px;opacity:.7">${m.file.size}</span>
        </div>
      ` : ''}
    </div>
  `).join('');
}

function escapeHtml(text) {
  const div = document.createElement('div');
  div.textContent = text;
  return div.innerHTML;
}

function togglePanel() {
  document.getElementById('adminPanel').classList.toggle('show');
  document.getElementById('adminActions').classList.add('hidden');
  document.getElementById('adminPassInput').value = '';
}

function closePanel() {
  document.getElementById('adminPanel').classList.remove('show');
}

function checkAdmin() {
  const pass = document.getElementById('adminPassInput').value;
  if (pass === ADMIN_PASS) {
    document.getElementById('adminActions').classList.remove('hidden');
  } else {
    alert('رمز اشتباه!');
  }
}

async function clearAllMsgs() {
  if (!confirm('همه پیام‌ها حذف شوند؟ بازگشت ندارد!')) return;
  msgs = [];
  lastSeenHash = '';
  if (await saveToCloud()) {
    alert('✅ همه پیام‌ها حذف شدند');
    renderMsgs();
    closePanel();
  }
}

// 🔄 بروزرسانی خودکار هر ۵ ثانیه (سریع‌تر شد!)
setInterval(loadMsgs, 5000);

// بارگذاری اولیه
loadMsgs();
</script>
</body>
</html>
