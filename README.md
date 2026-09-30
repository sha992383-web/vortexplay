<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>پنل مدیریت | VORTEXPLAY</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700;900&family=Rajdhani:wght@500;600;700&display=swap" rel="stylesheet">
<style>
:root {
    --gold: #FFD700; --gold-dark: #D4AF37; --blue-neon: #00D9FF;
    --dark-bg: #0B0B1A; --card-bg: rgba(20,15,40,0.9);
}
* { margin: 0; padding: 0; box-sizing: border-box; }
body {
    font-family: 'Rajdhani', sans-serif; min-height: 100vh; color: #E8E8FF;
    background: linear-gradient(135deg, #0B0B1A, #1A103C, #0F1A3C);
    display: flex; align-items: center; justify-content: center; padding: 20px;
}
.login-box, .panel {
    background: var(--card-bg); border: 2px solid var(--gold); border-radius: 16px;
    padding: 30px; max-width: 500px; width: 100%;
    box-shadow: 0 0 20px rgba(255,215,0,0.4);
}
h2 { font-family: 'Cinzel', serif; color: var(--gold); margin-bottom: 20px; text-align: center; }
input, textarea, select {
    width: 100%; padding: 12px 15px; margin: 8px 0 15px;
    background: rgba(255,255,255,0.08); border: 1px solid #444;
    border-radius: 8px; color: white; font-size: 1rem; font-family: inherit;
}
input:focus, textarea:focus { outline: none; border-color: var(--gold); }
button {
    padding: 12px 24px; border: none; border-radius: 8px; font-size: 1rem;
    font-weight: 700; cursor: pointer; transition: 0.2s; font-family: inherit;
}
.btn-primary { background: linear-gradient(135deg, var(--gold), var(--gold-dark)); color: #000; width: 100%; margin-top: 10px; }
.btn-primary:hover { transform: scale(1.02); }
.btn-secondary { background: #333; color: white; margin: 5px; }
.btn-danger { background: #C62828; color: white; }
.hidden { display: none !important; }
.tabs { display: flex; gap: 10px; margin-bottom: 20px; flex-wrap: wrap; }
.tab {
    padding: 10px 18px; background: #222; border-radius: 8px; cursor: pointer;
    border: none; color: #AAA; font-weight: 600;
}
.tab.active { background: var(--gold); color: #000; }
.msg-item {
    background: rgba(255,255,255,0.05); border-radius: 8px; padding: 15px;
    margin-bottom: 10px; border-right: 3px solid var(--gold);
}
.msg-item h4 { color: var(--gold); margin-bottom: 5px; }
.msg-item p { color: #CCC; font-size: 0.9rem; }
.note { font-size: 0.85rem; color: #888; margin-top: 15px; line-height: 1.6; }
.back-link {
    display: inline-block; margin-bottom: 20px; color: #888;
    text-decoration: none;
}
.back-link:hover { color: var(--gold); }
</style>
</head>
<body>

<div id="loginBox" class="login-box">
    <h2>🔐 ورود به پنل مدیریت</h2>
    <input type="password" id="adminPass" placeholder="رمز ۳۲ رقمی">
    <button class="btn-primary" onclick="checkPass()">ورود</button>
    <p class="note">رمز: K9#mP2$xR7!vL3@nQ5&bT1*wZ8%yA4^</p>
</div>

<div id="adminPanel" class="panel hidden">
    <a href="../" class="back-link">← بازگشت به سایت</a>
    <h2>⚙ پنل مدیریت VORTEXPLAY</h2>
    
    <div class="tabs">
        <button class="tab active" onclick="switchTab('add')">افزودن پیام</button>
        <button class="tab" onclick="switchTab('manage')">ویرایش/حذف</button>
    </div>

    <div id="tabAdd">
        <select id="catSelect">
            <option value="backup">💾 بکاپ</option>
            <option value="tutorial">📚 آموزش</option>
            <option value="news">📰 اخبار</option>
            <option value="gaming">🎮 گیمینگ</option>
        </select>
        <input type="text" id="msgTitle" placeholder="عنوان پیام">
        <textarea id="msgContent" rows="6" placeholder="متن پیام — می‌توانید لینک و توضیحات قرار دهید..."></textarea>
        <button class="btn-primary" onclick="saveMessage()">✅ ثبت پیام</button>
        <p class="note">⚠️ پس از ثبت، حدود ۱ دقیقه صبر کن تا سایت به‌روزرسانی شود.</p>
    </div>

    <div id="tabManage" class="hidden">
        <select id="manageCat" onchange="renderManageList()">
            <option value="backup">💾 بکاپ</option>
            <option value="tutorial">📚 آموزش</option>
            <option value="news">📰 اخبار</option>
            <option value="gaming">🎮 گیمینگ</option>
        </select>
        <div id="manageList" style="margin-top:15px;"></div>
    </div>
</div>

<script>
const ADMIN_PASSWORD = "K9#mP2$xR7!vL3@nQ5&bT1*wZ8%yA4^";
const CATEGORIES = {
    backup: 'بکاپ', tutorial: 'آموزش', news: 'اخبار', gaming: 'گیمینگ'
};
let messages = {};

async function loadData() {
    try {
        const res = await fetch('../messages.json?t=' + Date.now());
        messages = await res.json();
    } catch {
        messages = { backup:[], tutorial:[], news:[], gaming:[] };
    }
}

function checkPass() {
    if (document.getElementById('adminPass').value === ADMIN_PASSWORD) {
        document.getElementById('loginBox').classList.add('hidden');
        document.getElementById('adminPanel').classList.remove('hidden');
        loadData();
    } else {
        alert('❌ رمز اشتباه!');
    }
}

function switchTab(tab) {
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    event.target.classList.add('active');
    document.getElementById('tabAdd').classList.toggle('hidden', tab !== 'add');
    document.getElementById('tabManage').classList.toggle('hidden', tab !== 'manage');
    if (tab === 'manage') renderManageList();
}

async function saveMessage() {
    const cat = document.getElementById('catSelect').value;
    const title = document.getElementById('msgTitle').value.trim();
    const content = document.getElementById('msgContent').value.trim();
    
    if (!title || !content) return alert('⚠️ عنوان و متن را کامل کن!');
    
    await loadData();
    messages[cat].unshift({
        title, content,
        time: new Date().toLocaleString('fa-IR')
    });
    
    await updateJSON();
    alert('✅ پیام ثبت شد! سایت پس از چند دقیقه به‌روزرسانی می‌شود.');
    document.getElementById('msgTitle').value = '';
    document.getElementById('msgContent').value = '';
}

async function updateJSON() {
    const dataStr = JSON.stringify(messages, null, 2);
    alert('📋 این متن را کپی کن → به مخزن برو → فایل messages.json را ویرایش کن → جایگزین کن → Commit changes:\n\n' + dataStr);
}

function renderManageList() {
    const cat = document.getElementById('manageCat').value;
    const list = document.getElementById('manageList');
    const items = messages[cat] || [];
    if (!items.length) {
        list.innerHTML = '<p style="color:#666;">پیامی وجود ندارد.</p>';
        return;
    }
    list.innerHTML = items.map((msg, idx) => `
        <div class="msg-item">
            <h4>${escapeHtml(msg.title)}</h4>
            <p>${escapeHtml(msg.content.substring(0,60))}...</p>
            <small style="color:#666;">${msg.time}</small><br>
            <button class="btn-secondary" onclick="editItem('${cat}', ${idx})">ویرایش</button>
            <button class="btn-danger" onclick="deleteItem('${cat}', ${idx})">حذف</button>
        </div>
    `).join('');
}

function editItem(cat, idx) {
    const item = messages[cat][idx];
    document.getElementById('catSelect').value = cat;
    document.getElementById('msgTitle').value = item.title;
    document.getElementById('msgContent').value = item.content;
    switchTab('add');
    messages[cat].splice(idx, 1);
}

function deleteItem(cat, idx) {
    if (!confirm('مطمئنی؟')) return;
    messages[cat].splice(idx, 1);
    updateJSON();
    renderManageList();
}

function escapeHtml(t) {
    const d = document.createElement('div'); d.textContent = t; return d.innerHTML;
}
</script>
</body>
</html>
