<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Expires" content="0">
<title>VORTEXPLAY ☁️ نهایی</title>
<style>
:root {
  --gold: #FFD700;
  --orange: #FF6B00;
  --cyan: #00D9FF;
  --success: #00FF88;
  --error: #FF3366;
  --warn: #FFCC00;
  --bg-dark: #0A0418;
  --bg-card: rgba(25, 12, 50, 0.9);
  --border-gold: rgba(255, 215, 0, 0.35);
}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:Tahoma,sans-serif;min-height:100vh;
  background:linear-gradient(135deg,var(--bg-dark) 0%,#1A0A3C 50%,#2A1050 100%);
  color:#fff;padding:15px}
.container{max-width:650px;margin:0 auto}
.header{text-align:center;padding:25px 0 20px;
  border-bottom:2px solid transparent;
  border-image:linear-gradient(90deg,transparent,var(--gold),var(--orange),transparent) 1}
.logo{font-size:32px;font-weight:900;
  background:linear-gradient(90deg,var(--gold),var(--orange));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent}
.subtitle{color:#888;margin-top:8px;font-size:14px}
.card{background:var(--bg-card);border-radius:20px;padding:25px;margin-bottom:20px;
  border:1px solid var(--border-gold);backdrop-filter:blur(10px)}
input,textarea{width:100%;padding:14px;border-radius:12px;
  border:1px solid rgba(255,215,0,0.3);background:rgba(0,0,0,0.5);
  color:#fff;font-size:15px;margin-bottom:12px;outline:none}
input:focus,textarea:focus{border-color:var(--gold);box-shadow:0 0 10px rgba(255,215,0,0.3)}
button{width:100%;padding:15px;border-radius:12px;border:none;
  font-size:16px;font-weight:bold;cursor:pointer;transition:all .2s}
button:disabled{opacity:.6;cursor:not-allowed}
.btn-primary{background:linear-gradient(90deg,var(--gold),var(--orange));color:#000;margin-top:8px}
.btn-primary:active{transform:scale(.97)}
.btn-small{width:auto;padding:10px 18px;font-size:14px;
  background:rgba(0,217,255,.15);color:var(--cyan);border:1px solid rgba(0,217,255,0.3)}
.status{padding:12px;border-radius:10px;text-align:center;margin:12px 0;font-size:14px}
.ok{background:rgba(0,255,136,.15);color:var(--success);border:1px solid rgba(0,255,136,0.2)}
.wait{background:rgba(255,204,0,.15);color:var(--warn);border:1px solid rgba(255,204,0,0.2)}
.err{background:rgba(255,51,102,.15);color:var(--error);border:1px solid rgba(255,51,102,0.2)}
.msg{padding:16px;border-bottom:1px solid rgba(255,255,255,.1);animation:fadeIn .3s ease}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
.msg:last-child{border-bottom:none}
.name{color:var(--gold);font-weight:bold;margin-bottom:5px}
.time{color:#888;font-size:12px;margin-bottom:8px}
.empty{text-align:center;padding:50px 20px;color:#777}
.controls{display:flex;gap:10px;margin-top:15px;flex-wrap:wrap;align-items:center}
.refresh-info{font-size:12px;color:#666;margin-left:auto}
.file-label{display:inline-flex;align-items:center;gap:8px;padding:12px 18px;
  background:rgba(0,217,255,.15);border-radius:10px;color:var(--cyan);cursor:pointer;
  border:1px dashed rgba(0,217,255,0.3);margin:10px 0}
.file-info{color:var(--cyan);font-size:13px;margin-bottom:10px}
.hidden{display:none!important}
.admin-btn{position:fixed;top:15px;left:15px;width:48px;height:48px;border-radius:50%;
  border:none;background:linear-gradient(90deg,var(--gold),var(--orange));font-size:20px;
  cursor:pointer;z-index:999;box-shadow:0 0 15px rgba(255,215,0,0.3)}
.modal{position:fixed;inset:0;background:rgba(0,0,0,.92);z-index:1000;
  display:none;align-items:center;justify-content:center;padding:20px}
.modal.show{display:flex}
.modal-box{background:var(--bg-card);border-radius:20px;padding:25px;
  border:2px solid var(--gold);max-width:400px;width:100%}
</style>
</head>
<body>

<button class="admin-btn" onclick="openAdmin()">⚙️</button>

<div class="modal" id="adminModal">
  <div class="modal-box">
    <h3 style="color:var(--gold);text-align:center;margin-bottom:20px">🔐 پنل مدیریت</h3>
    <input type="password" id="adminPass" placeholder="رمز مدیریت را وارد کنید">
    <button class="btn-primary" onclick="checkAdmin()">ورود</button>
    <button class="btn-small" style="width:100%;margin-top:10px" onclick="closeAdmin()">بستن</button>
    <div id="adminActions" class="hidden" style="margin-top:20px">
      <p style="color:var(--success);text-align:center">✅ با موفقیت وارد شدید</p>
      <button class="btn-small" style="width:100%;margin-top:15px;
        background:rgba(255,51,102,.15);color:var(--error);border-color:var(--error)"
        onclick="clearAll()">🗑️ حذف همه پیام‌ها</button>
    </div>
  </div>
</div>

<div class="container">
  <div class="header">
    <h1 class="logo">👑 VORTEXPLAY</h1>
    <p class="subtitle">تابلو پیام‌رسانی ابری — همزمان و امن</p>
  </div>

  <div class="card">
    <input type="text" id="uName" placeholder="نام شما" maxlength="30">
    <textarea id="uMsg" placeholder="متن پیام خود را بنویسید..."></textarea>
    
    <label class="file-label">
      📁 انتخاب فایل
      <input type="file" id="uFile" class="hidden" onchange="showFileInfo()">
    </label>
    <p id="fileInfo" class="file-info"></p>
    
    <button class="btn-primary" id="sendBtn" onclick="sendMessage()">📤 ارسال پیام</button>
    <div id="status" class="status wait">⏳ در حال اتصال...</div>
    
    <div class="controls">
      <button class="btn-small" onclick="fetchMessages()">🔄 بروزرسانی دستی</button>
      <span class="refresh-info">🔄 هر ۵ ثانیه خودکار</span>
    </div>
  </div>

  <div class="card">
    <div id="messagesList"></div>
  </div>
</div>

<script>
// ==================================================
// ✅ تنظیمات — از قبل کامل شده! کاری نکن
const BIN_ID = '6ab5a0c1ac6210605af2700e';
const MASTER_KEY = '$2a$10$UjKZraBn9B.p9tfKZ6xzzuBs1uGDggLoZbjCdt9T9jVDor9.KGK56';
const ADMIN_PASSWORD = 'VORTEX2026';
const API = 'https://api.jsonbin.io/v3/b/' + BIN_ID;
const HEADERS = {
  'X-Master-Key': MASTER_KEY,
  'Content-Type': 'application/json'
};
let lastMessageId = null;
let isLoading = false;
// ==================================================

function showStatus(text, type = 'wait') {
  const el = document.getElementById('status');
  el.className = `status ${type}`;
  el.textContent = text;
}

function showFileInfo() {
  const file = document.getElementById('uFile').files[0];
  const info = document.getElementById('fileInfo');
  if (file) {
    info.textContent = `✅ ${file.name} (${(file.size / 1024).toFixed(1)} KB)`;
  } else {
    info.textContent = '';
  }
}

async function fetchMessages() {
  if (isLoading) return;
  isLoading = true;

  try {
    const res = await fetch(`${API}/latest?t=${Date.now()}`, {
      headers: HEADERS,
      cache: 'no-store'
    });

    if (!res.ok) throw new Error(`کد خطا: ${res.status}`);
    
    const data = await res.json();
    const messages = data.record.messages || [];
    
    const currentId = messages.length > 0 ? messages[0].id : 'EMPTY_LIST';
    
    if (currentId !== lastMessageId) {
      lastMessageId = currentId;
      renderMessages(messages);
      if (lastMessageId !== null) {
        showStatus(`✅ پیام جدید! مجموع: ${messages.length} پیام`, 'ok');
      } else {
        showStatus(`✅ متصل شد! ${messages.length} پیام موجود است`, 'ok');
      }
    }
  } catch (err) {
    showStatus(`❌ خطا: ${err.message}`, 'err');
    console.error('[Fetch Error]', err);
  } finally {
    isLoading = false;
  }
}

async function sendMessage() {
  const name = document.getElementById('uName').value.trim() || 'ناشناس';
  const text = document.getElementById('uMsg').value.trim();
  const file = document.getElementById('uFile').files[0];
  const sendBtn = document.getElementById('sendBtn');

  if (!text && !file) {
    alert('⚠️ لطفاً متنی بنویسید یا فایلی انتخاب کنید!');
    return;
  }

  sendBtn.disabled = true;
  sendBtn.textContent = '⏳ در حال ارسال...';
  showStatus('⏳ در حال ارسال پیام...');

  try {
    // دریافت لیست فعلی
    const prevRes = await fetch(`${API}/latest?t=${Date.now()}`, {
      headers: HEADERS,
      cache: 'no-store'
    });
    if (!prevRes.ok) throw new Error('دریافت لیست قبلی ناموفق');
    
    const prevData = await prevRes.json();
    const allMessages = prevData.record.messages || [];

    // اطلاعات فایل
    let fileData = null;
    if (file) {
      fileData = {
        name: file.name,
        size: (file.size / 1024).toFixed(1) + ' KB'
      };
    }

    // اضافه کردن پیام جدید
    allMessages.unshift({
      id: Date.now(),
      name: name,
      text: text,
      file: fileData,
      time: new Date().toLocaleString('fa-IR')
    });

    // ارسال به سرور
    const putRes = await fetch(API, {
      method: 'PUT',
      headers: HEADERS,
      body: JSON.stringify({ messages: allMessages })
    });

    if (!putRes.ok) throw new Error(`خطای سرور: ${putRes.status}`);

    // موفقیت
    showStatus('✅ پیام ارسال شد!', 'ok');
    document.getElementById('uMsg').value = '';
    document.getElementById('uFile').value = '';
    document.getElementById('fileInfo').textContent = '';
    lastMessageId = allMessages[0].id;
    renderMessages(allMessages);

  } catch (err) {
    showStatus(`❌ خطا: ${err.message}`, 'err');
    alert(`خطا در ارسال:\n${err.message}\nلطفاً دوباره تلاش کنید.`);
  } finally {
    sendBtn.disabled = false;
    sendBtn.textContent = '📤 ارسال پیام';
  }
}

function renderMessages(messages) {
  const container = document.getElementById('messagesList');
  
  if (!messages.length) {
    container.innerHTML = `
      <div class="empty">
        📭 هنوز هیچ پیامی ارسال نشده است.<br>
        اولین پیام را شما بنویسید! ✍️
      </div>
    `;
    return;
  }

  container.innerHTML = messages.map(msg => `
    <div class="msg">
      <div class="name">👤 ${escapeHtml(msg.name)}</div>
      <div class="time">${msg.time}</div>
      ${msg.text ? `<div style="margin:8px 0;line-height:1.8">${escapeHtml(msg.text)}</div>` : ''}
      ${msg.file ? `
        <div style="margin-top:10px;padding:10px;background:rgba(0,217,255,.1);border-radius:8px;
          border-left:3px solid var(--cyan)">
          📁 <strong>${escapeHtml(msg.file.name)}</strong>
          <span style="color:#888;font-size:12px;margin-left:8px">(${msg.file.size})</span>
        </div>
      ` : ''}
    </div>
  `).join('');
}

function escapeHtml(text) {
  if (!text) return '';
  const div = document.createElement('div');
  div.textContent = text;
  return div.innerHTML;
}

// پنل مدیریت
function openAdmin() {
  document.getElementById('adminModal').classList.add('show');
  document.getElementById('adminPass').value = '';
  document.getElementById('adminActions').classList.add('hidden');
}
function closeAdmin() {
  document.getElementById('adminModal').classList.remove('show');
}
function checkAdmin() {
  const pass = document.getElementById('adminPass').value;
  if (pass === ADMIN_PASSWORD) {
    document.getElementById('adminActions').classList.remove('hidden');
  } else {
    alert('❌ رمز عبور اشتباه است!');
  }
}
async function clearAll() {
  if (!confirm('⚠️ هشدار!\nهمه پیام‌ها برای همیشه حذف می‌شوند.\nادامه می‌دهید؟')) return;
  if (!confirm('⚠️ تأیید نهایی:\nبازگشت ندارد! مطمئن هستید؟')) return;

  try {
    showStatus('⏳ در حال حذف...');
    await fetch(API, {
      method: 'PUT',
      headers: HEADERS,
      body: JSON.stringify({ messages: [] })
    });
    lastMessageId = 'EMPTY_LIST';
    renderMessages([]);
    showStatus('✅ همه پیام‌ها حذف شدند', 'ok');
    closeAdmin();
  } catch (err) {
    alert(`خطا: ${err.message}`);
    showStatus('❌ خطا در حذف', 'err');
  }
}

// میانبر
document.addEventListener('keydown', e => {
  if (e.ctrlKey && e.key === 'Enter') sendMessage();
});

// شروع
setInterval(fetchMessages, 5000);
fetchMessages();
</script>
</body>
</html>

    <button class="btn btn-primary" id="sendButton" onclick="submitMessage()">📤 ارسال پیام به همه</button>
    
    <div id="statusDisplay" class="status wait">⏳ در حال اتصال به سرور...</div>
    
    <div class="controls">
      <button class="btn btn-secondary" onclick="fetchMessagesFromServer()">🔄 بروزرسانی</button>
      <span class="refresh-info">🔄 هر ۵ ثانیه به‌روز می‌شود</span>
    </div>
  </div>

  <!-- بخش نمایش پیام‌ها -->
  <div class="card">
    <h3 class="card-header">📬 پیام‌های عمومی</h3>
    <div id="messagesContainer">
      <div class="empty-state">
        <div class="empty-icon">📭</div>
        <p>هنوز هیچ پیامی ارسال نشده است.</p>
        <p style="font-size:13px; margin-top:8px">اولین پیام را شما بنویسید!</p>
      </div>
    </div>
  </div>
</div>

<script>
// ==================================================
// ⚙️ تنظیمات اصلی — از قبل کامل شده!
const CONFIG = {
  BIN_ID: '6ab5a0c1ac6210605af2700e',
  MASTER_KEY: '$2a$10$UjKZraBn9B.p9tfKZ6xzzuBs1uGDggLoZbjCdt9T9jVDor9.KGK56',
  ADMIN_PASSWORD: 'VORTEX2026',
  REFRESH_INTERVAL_MS: 5000,
  MAX_MESSAGES_DISPLAY: 100,
  MAX_MESSAGE_LENGTH: 5000
};

const API_BASE_URL = `https://api.jsonbin.io/v3/b/${CONFIG.BIN_ID}`;
const HTTP_HEADERS = {
  'X-Master-Key': CONFIG.MASTER_KEY,
  'Content-Type': 'application/json'
};

// حالت برنامه
let applicationState = {
  messages: [],
  lastKnownMessageId: null,
  isLoading: false,
  lastFetchTimestamp: 0,
  consecutiveErrors: 0
};

// ==================================================
// 📊 نمایش وضعیت
function updateStatusDisplay(text, type = 'wait') {
  const el = document.getElementById('statusDisplay');
  el.className = `status ${type}`;
  el.textContent = text;
}

// 📁 مدیریت فایل
function handleFileSelection() {
  const fileInput = document.getElementById('fileAttachmentInput');
  const display = document.getElementById('selectedFileNameDisplay');
  
  if (fileInput.files.length > 0) {
    const file = fileInput.files[0];
    const sizeKB = (file.size / 1024).toFixed(2);
    display.textContent = `✅ فایل انتخاب شده: ${file.name} (${sizeKB} KB)`;
  } else {
    display.textContent = '';
  }
}

// 🔄 دریافت پیام‌ها از سرور
async function fetchMessagesFromServer(force = false) {
  if (applicationState.isLoading && !force) return;
  
  applicationState.isLoading = true;
  
  try {
    const timestamp = Date.now();
    const response = await fetch(`${API_BASE_URL}/latest?t=${timestamp}`, {
      headers: HTTP_HEADERS,
      cache: 'no-store',
      signal: AbortSignal.timeout ? AbortSignal.timeout(15000) : undefined
    });

    if (!response.ok) {
      throw new Error(`کد خطا: ${response.status}`);
    }

    const data = await response.json();
    
    if (!data || !data.record) {
      throw new Error('پاسخ نامعتبر از سرور');
    }

    const messages = data.record.messages || [];
    
    // بررسی تغییر
    const latestId = messages.length > 0 ? messages[0].id : 'EMPTY_LIST';
    
    if (latestId !== applicationState.lastKnownMessageId || force) {
      applicationState.messages = messages.slice(0, CONFIG.MAX_MESSAGES_DISPLAY);
      applicationState.lastKnownMessageId = latestId;
      renderAllMessages();
      
      if (applicationState.lastKnownMessageId !== null && !force) {
        updateStatusDisplay(`✅ پیام جدید دریافت شد! مجموعاً ${messages.length} پیام`, 'ok');
      } else {
        updateStatusDisplay(`✅ متصل شد! ${messages.length} پیام موجود است`, 'ok');
      }
    }

    applicationState.consecutiveErrors = 0;
    
  } catch (error) {
    applicationState.consecutiveErrors++;
    const errorMsg = error.message || 'خطای نامشخص';
    
    if (applicationState.consecutiveErrors >= 3) {
      updateStatusDisplay(`❌ خطای مکرر: ${errorMsg} — لطفاً صفحه را بازنشانی کنید`, 'err');
    } else {
      updateStatusDisplay(`⚠️ خطا در دریافت: ${errorMsg}`, 'warn');
    }
    
    console.error('[VORTEXPLAY Fetch Error]', error);
  } finally {
    applicationState.isLoading = false;
    applicationState.lastFetchTimestamp = Date.now();
  }
}

// 📤 ارسال پیام جدید
async function submitMessage() {
  const nameInput = document.getElementById('senderNameInput');
  const textInput = document.getElementById('messageTextInput');
  const fileInput = document.getElementById('fileAttachmentInput');
  const sendBtn = document.getElementById('sendButton');

  const name = nameInput.value.trim() || 'ناشناس';
  const text = textInput.value.trim();
  const file = fileInput.files[0];

  // اعتبارسنجی
  if (!text && !file) {
    alert('⚠️ لطفاً متنی بنویسید یا فایلی انتخاب کنید!');
    textInput.focus();
    return;
  }

  if (text.length > CONFIG.MAX_MESSAGE_LENGTH) {
    alert(`⚠️ طول پیام بیش از حد مجاز است (حداکثر ${CONFIG.MAX_MESSAGE_LENGTH} کاراکتر)`);
    return;
  }

  // غیرفعال کردن دکمه
  sendBtn.disabled = true;
  sendBtn.textContent = '⏳ در حال ارسال...';
  updateStatusDisplay('⏳ در حال ارسال پیام به سرور...', 'wait');

  try {
    // ساخت اطلاعات فایل
    let fileInfo = null;
    if (file) {
      fileInfo = {
        name: file.name,
        sizeBytes: file.size,
        sizeDisplay: (file.size / 1024).toFixed(2) + ' KB',
        type: file.type || 'application/octet-stream'
      };
    }

    // دریافت لیست فعلی از سرور
    const timestamp = Date.now();
    const prevResponse = await fetch(`${API_BASE_URL}/latest?t=${timestamp}`, {
      headers: HTTP_HEADERS,
      cache: 'no-store'
    });

    if (!prevResponse.ok) {
      throw new Error('دریافت لیست قبلی ناموفق بود');
    }

    const prevData = await prevResponse.json();
    const allMessages = prevData.record.messages || [];

    // اضافه کردن پیام جدید به ابتدای لیست
    const newMessage = {
      id: Date.now(),
      sender: name,
      text: text,
      attachment: fileInfo,
      timestamp: new Date().toISOString(),
      displayTime: new Date().toLocaleString('fa-IR')
    };

    allMessages.unshift(newMessage);

    // ارسال کل لیست به سرور
    const putResponse = await fetch(API_BASE_URL, {
      method: 'PUT',
      headers: HTTP_HEADERS,
      body: JSON.stringify({ messages: allMessages })
    });

    if (!putResponse.ok) {
      throw new Error(`خطای سرور: ${putResponse.status}`);
    }

    // موفقیت
    updateStatusDisplay('✅ پیام شما با موفقیت ارسال شد!', 'ok');
    
    // پاک کردن فرم
    textInput.value = '';
    fileInput.value = '';
    document.getElementById('selectedFileNameDisplay').textContent = '';
    
    // به‌روزرسانی فوری
    applicationState.messages = allMessages.slice(0, CONFIG.MAX_MESSAGES_DISPLAY);
    applicationState.lastKnownMessageId = allMessages[0].id;
    renderAllMessages();

  } catch (error) {
    console.error('[VORTEXPLAY Send Error]', error);
    updateStatusDisplay(`❌ خطا: ${error.message}`, 'err');
    alert(`خطا در ارسال: ${error.message}\nلطفاً دوباره تلاش کنید.`);
  } finally {
    sendBtn.disabled = false;
    sendBtn.textContent = '📤 ارسال پیام به همه';
  }
}

// 📝 نمایش پیام‌ها
function renderAllMessages() {
  const container = document.getElementById('messagesContainer');
  const messages = applicationState.messages;

  if (!messages || messages.length === 0) {
    container.innerHTML = `
      <div class="empty-state">
        <div class="empty-icon">📭</div>
        <p>هنوز هیچ پیامی ارسال نشده است.</p>
        <p style="font-size:13px; margin-top:8px">اولین پیام را شما بنویسید!</p>
      </div>
    `;
    return;
  }

  container.innerHTML = messages.map(msg => {
    const hasText = msg.text && msg.text.trim().length > 0;
    const hasFile = msg.attachment !== null;

    return `
      <div class="msg">
        <div class="msg-header">
          <span class="msg-author">👤 ${escapeHtml(msg.sender || 'ناشناس')}</span>
          <span class="msg-time">${msg.displayTime || '-'}</span>
        </div>
        ${hasText ? `<div class="msg-body">${escapeHtml(msg.text)}</div>` : ''}
        ${hasFile ? `
          <div class="msg-file">
            📁 <strong>${escapeHtml(msg.attachment.name)}</strong>
            <span style="color:${'var(--text-dim)'}; font-size:12px; margin-left:8px">(${escapeHtml(msg.attachment.sizeDisplay)})</span>
          </div>
        ` : ''}
      </div>
    `;
  }).join('');
}

// 🔐 امنیت: جلوگیری از اجرای کد مخرب
function escapeHtml(text) {
  if (!text) return '';
  const div = document.createElement('div');
  div.textContent = text;
  return div.innerHTML;
}

// ⚙️ پنل مدیریت
function openAdminPanel() {
  document.getElementById('adminPanelOverlay').classList.add('show');
  document.getElementById('adminPasswordInput').value = '';
  document.getElementById('adminActionsArea').classList.add('hidden');
}

function closeAdminPanel() {
  document.getElementById('adminPanelOverlay').classList.remove('show');
}

function verifyAdmin() {
  const input = document.getElementById('adminPasswordInput').value;
  if (input === CONFIG.ADMIN_PASSWORD) {
    document.getElementById('adminActionsArea').classList.remove('hidden');
  } else {
    alert('❌ رمز عبور اشتباه است!');
  }
}

async function confirmClearAllMessages() {
  if (!confirm('⚠️ هشدار!\nهمه پیام‌ها برای همیشه حذف می‌شوند.\nادامه می‌دهید؟')) {
    return;
  }

  if (!confirm('⚠️ آخرین تأیید:\nآیا مطمئن هستید؟ این عملیات بازگشت‌ناپذیر است!')) {
    return;
  }

  try {
    updateStatusDisplay('⏳ در حال حذف تمام پیام‌ها...', 'wait');
    
    await fetch(API_BASE_URL, {
      method: 'PUT',
      headers: HTTP_HEADERS,
      body: JSON.stringify({ messages: [] })
    });

    applicationState.messages = [];
    applicationState.lastKnownMessageId = 'EMPTY_LIST';
    renderAllMessages();
    
    updateStatusDisplay('✅ همه پیام‌ها حذف شدند', 'ok');
    closeAdminPanel();
    
  } catch (error) {
    alert(`خطا در حذف: ${error.message}`);
    updateStatusDisplay('❌ خطا در حذف', 'err');
  }
}

function forceRefreshFromServer() {
  fetchMessagesFromServer(true);
  alert('🔄 بروزرسانی اجباری انجام شد!');
}

// ⌨️ میانبرها
document.addEventListener('keydown', function(e) {
  if (e.ctrlKey && e.key === 'Enter') {
    submitMessage();
  }
});

// 🔄 شروع خودکار
document.addEventListener('DOMContentLoaded', function() {
  fetchMessagesFromServer();
  setInterval(fetchMessagesFromServer, CONFIG.REFRESH_INTERVAL_MS);
});
</script>
</body>
</html>
