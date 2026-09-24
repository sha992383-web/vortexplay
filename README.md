<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Expires" content="0">
<title>VORTEXPLAY ☁️ تابلو ابری امن</title>
<style>
:root {
  --gold: #FFD700;
  --gold-dark: #CCAA00;
  --orange: #FF6B00;
  --orange-dark: #CC5500;
  --cyan: #00D9FF;
  --cyan-dark: #00A8CC;
  --success: #00FF88;
  --success-bg: rgba(0, 255, 136, 0.15);
  --error: #FF3366;
  --error-bg: rgba(255, 51, 102, 0.15);
  --warn: #FFCC00;
  --warn-bg: rgba(255, 204, 0, 0.15);
  --bg-dark: #0A0418;
  --bg-card: rgba(25, 12, 50, 0.9);
  --bg-input: rgba(0, 0, 0, 0.5);
  --border-gold: rgba(255, 215, 0, 0.35);
  --border-cyan: rgba(0, 217, 255, 0.35);
  --text-light: #E0E0FF;
  --text-dim: #8888AA;
  --shadow-glow: 0 0 25px rgba(255, 215, 0, 0.25);
  --shadow-cyan: 0 0 15px rgba(0, 217, 255, 0.2);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Tahoma', 'Vazirmatn', sans-serif;
  min-height: 100vh;
  background: linear-gradient(135deg, var(--bg-dark) 0%, #1A0A3C 40%, #2A1050 70%, var(--bg-dark) 100%);
  color: var(--text-light);
  padding: 15px;
  line-height: 1.6;
}

.container {
  max-width: 680px;
  margin: 0 auto;
}

.header {
  text-align: center;
  padding: 30px 20px;
  margin-bottom: 25px;
  border-bottom: 2px solid transparent;
  border-image: linear-gradient(90deg, transparent, var(--gold), var(--orange), var(--gold), transparent) 1;
}

.logo {
  font-size: 32px;
  font-weight: 900;
  background: linear-gradient(90deg, var(--gold) 0%, var(--orange) 50%, var(--gold) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  letter-spacing: 1px;
  text-shadow: 0 0 30px rgba(255, 215, 0, 0.3);
  margin-bottom: 5px;
}

.subtitle {
  color: var(--text-dim);
  font-size: 14px;
}

.version {
  font-size: 11px;
  color: #555;
  margin-top: 8px;
}

.card {
  background: var(--bg-card);
  border-radius: 20px;
  padding: 25px;
  margin-bottom: 22px;
  border: 1px solid var(--border-gold);
  box-shadow: var(--shadow-glow);
  backdrop-filter: blur(12px);
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-2px);
}

.card-header {
  font-size: 18px;
  font-weight: bold;
  color: var(--gold);
  margin-bottom: 18px;
  padding-bottom: 10px;
  border-bottom: 1px dashed var(--border-gold);
}

.input-group {
  margin-bottom: 14px;
}

label.input-label {
  display: block;
  font-size: 13px;
  color: var(--text-dim);
  margin-bottom: 6px;
}

input[type="text"],
textarea {
  width: 100%;
  padding: 14px 16px;
  border-radius: 12px;
  border: 1px solid var(--border-gold);
  background: var(--bg-input);
  color: var(--text-light);
  font-size: 15px;
  outline: none;
  transition: all 0.3s ease;
  font-family: inherit;
}

input[type="text"]:focus,
textarea:focus {
  border-color: var(--gold);
  box-shadow: 0 0 12px rgba(255, 215, 0, 0.35);
  background: rgba(0, 0, 0, 0.6);
}

textarea {
  min-height: 120px;
  resize: vertical;
}

.btn {
  width: 100%;
  padding: 15px;
  border-radius: 12px;
  border: none;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 8px;
  font-family: inherit;
}

.btn-primary {
  background: linear-gradient(90deg, var(--gold) 0%, var(--orange) 100%);
  color: #000;
  box-shadow: 0 4px 15px rgba(255, 107, 0, 0.3);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(255, 107, 0, 0.45);
}

.btn-primary:active {
  transform: scale(0.97);
}

.btn-secondary {
  background: rgba(0, 217, 255, 0.15);
  color: var(--cyan);
  border: 1px solid var(--border-cyan);
  width: auto;
  padding: 10px 18px;
  font-size: 14px;
}

.btn-secondary:hover {
  background: rgba(0, 217, 255, 0.25);
  box-shadow: var(--shadow-cyan);
}

.btn-danger {
  background: rgba(255, 51, 102, 0.15);
  color: var(--error);
  border: 1px solid var(--error);
  width: auto;
  padding: 10px 18px;
  font-size: 14px;
}

.btn-danger:hover {
  background: rgba(255, 51, 102, 0.25);
}

.status {
  padding: 12px 16px;
  border-radius: 10px;
  font-size: 14px;
  margin-top: 15px;
  text-align: center;
  font-weight: 500;
  transition: all 0.3s ease;
}

.status.ok {
  background: var(--success-bg);
  color: var(--success);
  border: 1px solid rgba(0, 255, 136, 0.3);
}

.status.wait {
  background: var(--warn-bg);
  color: var(--warn);
  border: 1px solid rgba(255, 204, 0, 0.3);
}

.status.err {
  background: var(--error-bg);
  color: var(--error);
  border: 1px solid rgba(255, 51, 102, 0.3);
}

.controls {
  display: flex;
  gap: 10px;
  margin-top: 15px;
  flex-wrap: wrap;
  align-items: center;
}

.refresh-info {
  font-size: 12px;
  color: var(--text-dim);
  margin-right: auto;
}

.file-area {
  margin-top: 5px;
}

.file-label {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 12px 18px;
  background: rgba(0, 217, 255, 0.15);
  border-radius: 10px;
  color: var(--cyan);
  cursor: pointer;
  font-size: 14px;
  border: 1px dashed var(--border-cyan);
  transition: all 0.3s ease;
}

.file-label:hover {
  background: rgba(0, 217, 255, 0.25);
  border-style: solid;
}

.file-name {
  margin-top: 8px;
  font-size: 13px;
  color: var(--cyan);
}

.hidden {
  display: none !important;
}

/* پیام‌ها */
.msg {
  padding: 18px 16px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  animation: fadeSlideIn 0.4s ease forwards;
  opacity: 0;
  transform: translateY(10px);
}

@keyframes fadeSlideIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.msg:first-child {
  animation-delay: 0.05s;
}

.msg:nth-child(2) {
  animation-delay: 0.1s;
}

.msg:nth-child(3) {
  animation-delay: 0.15s;
}

.msg:last-child {
  border-bottom: none;
}

.msg-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
  flex-wrap: wrap;
  gap: 6px;
}

.msg-author {
  color: var(--gold);
  font-weight: bold;
  font-size: 15px;
}

.msg-time {
  color: var(--text-dim);
  font-size: 12px;
}

.msg-body {
  line-height: 1.8;
  font-size: 15px;
  white-space: pre-wrap;
  word-break: break-word;
  color: #fff;
}

.msg-file {
  margin-top: 12px;
  padding: 12px 14px;
  background: rgba(0, 217, 255, 0.1);
  border-radius: 10px;
  border-left: 3px solid var(--cyan);
  font-size: 14px;
}

.empty-state {
  text-align: center;
  padding: 50px 20px;
  color: var(--text-dim);
}

.empty-icon {
  font-size: 40px;
  margin-bottom: 15px;
  opacity: 0.5;
}

/* پنل مدیریت */
.admin-toggle {
  position: fixed;
  top: 15px;
  left: 15px;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: none;
  background: linear-gradient(135deg, var(--gold), var(--orange));
  font-size: 20px;
  cursor: pointer;
  z-index: 999;
  box-shadow: 0 0 15px rgba(255, 215, 0, 0.4);
  transition: transform 0.3s ease;
}

.admin-toggle:hover {
  transform: scale(1.1);
}

.admin-panel {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.92);
  z-index: 1000;
  display: none;
  align-items: center;
  justify-content: center;
  padding: 20px;
}

.admin-panel.show {
  display: flex;
}

.admin-box {
  background: var(--bg-card);
  border-radius: 20px;
  padding: 30px;
  border: 2px solid var(--gold);
  box-shadow: 0 0 30px rgba(255, 215, 0, 0.25);
  max-width: 420px;
  width: 100%;
}

.admin-title {
  color: var(--gold);
  text-align: center;
  margin-bottom: 20px;
  font-size: 20px;
}

.admin-success {
  color: var(--success);
  text-align: center;
  margin: 15px 0;
  padding: 10px;
  background: var(--success-bg);
  border-radius: 8px;
}

/* موبایل */
@media (max-width: 480px) {
  .logo { font-size: 24px; }
  .card { padding: 18px; }
  .controls { flex-direction: column; align-items: stretch; }
  .refresh-info { margin-right: 0; text-align: center; }
}
</style>
</head>
<body>

<button class="admin-toggle" id="adminToggleBtn" onclick="openAdminPanel()">⚙️</button>

<div class="admin-panel" id="adminPanelOverlay">
  <div class="admin-box">
    <h2 class="admin-title">🔐 پنل مدیریت VORTEXPLAY</h2>
    <div class="input-group">
      <label class="input-label">رمز مدیریت</label>
      <input type="password" id="adminPasswordInput" placeholder="رمز را وارد کنید...">
    </div>
    <button class="btn btn-primary" onclick="verifyAdmin()">ورود به پنل</button>
    <button class="btn btn-secondary" style="margin-top:10px; width:100%" onclick="closeAdminPanel()">بستن</button>
    
    <div id="adminActionsArea" class="hidden">
      <div class="admin-success">✅ با موفقیت وارد شدید</div>
      <button class="btn btn-danger" style="margin-top:15px" onclick="confirmClearAllMessages()">🗑️ حذف کامل همه پیام‌ها</button>
      <button class="btn btn-secondary" style="margin-top:10px; width:100%" onclick="forceRefreshFromServer()">🔄 بروزرسانی اجباری از سرور</button>
    </div>
  </div>
</div>

<div class="container">
  <div class="header">
    <h1 class="logo">👑 VORTEXPLAY</h1>
    <p class="subtitle">تابلو پیام‌رسانی ابری امن و همزمان</p>
    <p class="version">نسخه ۲.۱.۰ | پایدار و سریع</p>
  </div>

  <!-- بخش ارسال -->
  <div class="card">
    <h3 class="card-header">✍️ ارسال پیام جدید</h3>
    
    <div class="input-group">
      <label class="input-label">نام شما</label>
      <input type="text" id="senderNameInput" placeholder="نام یا نام مستعار خود را بنویسید" maxlength="30" autocomplete="off">
    </div>

    <div class="input-group">
      <label class="input-label">متن پیام</label>
      <textarea id="messageTextInput" placeholder="متن پیام خود را اینجا بنویسید..."></textarea>
    </div>

    <div class="file-area">
      <label class="file-label">
        📁 پیوست فایل
        <input type="file" id="fileAttachmentInput" class="hidden" onchange="handleFileSelection()">
      </label>
      <div id="selectedFileNameDisplay" class="file-name"></div>
    </div>

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
