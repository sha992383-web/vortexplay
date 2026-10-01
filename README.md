<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEX PLAY | PS5 Jailbreak Host</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@500;600;700&display=swap" rel="stylesheet">
<style>
:root {
    --bg-main: #050508;
    --bg-card: #0f0f1a;
    --bg-glow: #1a1a2e;
    --accent-green: #00ff88;
    --accent-cyan: #00ccff;
    --accent-gold: #ffd700;
    --text-primary: #e6e6e6;
    --text-dim: #888899;
    --border-glow: rgba(0, 255, 136, 0.3);
}
* { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
body {
    background: radial-gradient(circle at top, #101020 0%, #050508 70%);
    min-height: 100vh; color: var(--text-primary); padding: 20px;
}
.container { max-width: 900px; margin: 0 auto; }

/* ===== HEADER ===== */
header {
    text-align: center; padding: 40px 20px 30px;
    border-bottom: 1px solid rgba(0,255,136,0.15); margin-bottom: 30px;
}
.logo {
    font-size: 2.8rem; font-weight: 700; letter-spacing: 3px;
    background: linear-gradient(135deg, var(--accent-green), var(--accent-cyan));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    text-shadow: 0 0 40px rgba(0,255,136,0.3);
}
.subtitle { color: var(--text-dim); margin-top: 8px; font-size: 1.1rem; }
.status-bar {
    display: inline-flex; align-items: center; gap: 8px; margin-top: 15px;
    background: rgba(0,255,136,0.08); padding: 8px 20px; border-radius: 30px;
    border: 1px solid rgba(0,255,136,0.2);
}
.status-dot {
    width: 10px; height: 10px; background: var(--accent-green); border-radius: 50%;
    animation: pulse 2s infinite;
}
@keyframes pulse {
    0%,100% { opacity: 1; box-shadow: 0 0 6px var(--accent-green); }
    50% { opacity: 0.4; }
}
.version { font-size: 0.9rem; color: var(--accent-cyan); margin-left: 10px; }

/* ===== CARDS ===== */
.card {
    background: var(--bg-card); border-radius: 16px; padding: 25px; margin-bottom: 20px;
    border: 1px solid rgba(0,255,136,0.1);
    box-shadow: 0 0 20px rgba(0,255,136,0.05);
    transition: transform 0.2s, border-color 0.2s;
}
.card:hover { border-color: var(--border-glow); transform: translateY(-2px); }
.card h2 {
    color: var(--accent-green); font-size: 1.3rem; margin-bottom: 18px;
    display: flex; align-items: center; gap: 10px;
}

/* ===== BUTTONS ===== */
.btn-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 12px; }
.btn {
    background: linear-gradient(135deg, #1a1a2e, #0f0f1a);
    border: 1px solid rgba(0,255,136,0.2); border-radius: 10px; padding: 15px 20px;
    color: var(--text-primary); font-size: 1rem; font-weight: 600; cursor: pointer;
    transition: all 0.2s; text-align: center; text-decoration: none; display: inline-block;
}
.btn:hover {
    border-color: var(--accent-green); background: rgba(0,255,136,0.08);
    transform: translateY(-2px); box-shadow: 0 5px 15px rgba(0,255,136,0.15);
}
.btn.primary {
    background: linear-gradient(135deg, var(--accent-green), var(--accent-cyan));
    color: #000; border: none;
}
.btn.danger { border-color: rgba(255,68,68,0.3); }
.btn.danger:hover { border-color: #ff4444; background: rgba(255,68,68,0.1); }

/* ===== LOG CONSOLE ===== */
.console {
    background: #0a0a12; border-radius: 10px; padding: 20px;
    font-family: 'Courier New', monospace; font-size: 0.9rem;
    color: #b0f0c0; border: 1px solid #1a3025;
    max-height: 250px; overflow-y: auto; direction: ltr; text-align: left;
}
.console-line { margin: 4px 0; line-height: 1.5; }
.log-info { color: #88ccff; }
.log-success { color: #88ff88; }
.log-warn { color: #ffcc44; }
.log-error { color: #ff6666; }

/* ===== ADMIN PANEL ===== */
.admin-section { margin-top: 30px; padding-top: 20px; border-top: 1px dashed rgba(0,255,136,0.2); }
.admin-input {
    width: 100%; padding: 12px 15px; margin: 8px 0;
    background: #0a0a12; border: 1px solid #222; border-radius: 8px;
    color: white; font-size: 1rem;
}
.admin-input:focus { outline: none; border-color: var(--accent-cyan); }
.hidden { display: none !important; }

/* ===== FOOTER ===== */
footer {
    text-align: center; margin-top: 40px; padding: 20px;
    color: var(--text-dim); font-size: 0.9rem;
}
footer a { color: var(--accent-cyan); text-decoration: none; }

/* ===== WARNING BOX ===== */
.warning-box {
    background: rgba(255,68,68,0.08); border: 1px solid rgba(255,68,68,0.25);
    border-radius: 10px; padding: 15px; margin-top: 20px; color: #ffb0b0;
}
.dns-box {
    background: #0f1a2e; padding: 15px; border-radius: 8px;
    font-family: monospace; font-size: 1.1rem; margin: 12px 0;
    border-right: 3px solid var(--accent-cyan);
}
</style>
</head>
<body>
<div class="container">

<header>
    <h1 class="logo">VORTEX PLAY</h1>
    <p class="subtitle">پیشرفته‌ترین میزبان تخصصی ابزارها و اکسپلویت‌های کنسول</p>
    <div class="status-bar">
        <span class="status-dot"></span>
        <span>سیستم: آماده برای اجرا</span>
        <span class="version">نسخه: v2.5 — Stable</span>
    </div>
</header>

<!-- ===== MAIN DASHBOARD ===== -->
<div id="main-panel">

<div class="card">
    <h2>📡 تنظیمات اتصال</h2>
    <p>قبل از اجرای اکسپلویت، DNS کنسول را به صورت زیر تنظیم کنید:</p>
    <div class="dns-box">
        DNS اصلی: <strong style="color:var(--accent-green)">45.56.67.85</strong><br>
        DNS فرعی: <span style="color:#666">— خالی بگذارید —</span>
    </div>
</div>

<div class="card">
    <h2>⚡ دسترسی سریع</h2>
    <div class="btn-grid">
        <a href="https://jordyidk.github.io/slopkit/" target="_blank" class="btn primary">🚀 اجرای اکسپلویت</a>
        <button onclick="addLog('info', 'آماده‌سازی بارگذاری پیلودها...')" class="btn">📦 بارگذاری پیلود</button>
        <button onclick="addLog('info', 'بررسی وضعیت سیستم عامل...')" class="btn">ℹ️ اطلاعات کنسول</button>
        <button onclick="addLog('warn', 'مسدودسازی سرورهای سونی فعال شد')" class="btn danger">🛡️ مسدودسازی آپدیت</button>
    </div>
</div>

<div class="card">
    <h2>📋 پیلودهای پیشنهادی</h2>
    <p style="color:#888; margin-bottom:12px">پس از موفقیت اکسپلویت، به ترتیب اجرا کنید:</p>
    <div style="line-height:2.2; font-size:0.95rem">
        ✅ <strong>kstuff-lite.elf</strong> — ابزارهای پایه<br>
        ✅ <strong>ShadowMountPlus.elf</strong> — نصب بکاپ و بازی<br>
        ✅ <strong>etaHEN.elf</strong> — محیط هوم‌برو<br>
        ✅ <strong>nanoDNS.elf</strong> — مسدودسازی دائمی سرورهای سونی
    </div>
</div>

<div class="card">
    <h2>🖥️ لاگ سیستم</h2>
    <div class="console" id="log-console">
        <div class="console-line log-success">[Vortex Engine] سیستم با موفقیت بارگذاری شد...</div>
        <div class="console-line log-info">[Info] منتظر انتخاب کاربر برای اجرای پیلود...</div>
    </div>
</div>

<div class="warning-box">
    ⚠️ <strong>هشدار مهم:</strong><br>
    • فقط روی فریمور <strong>۷.۰۰ تا ۱۳.۶۰</strong> کار می‌کند<br>
    • نسخه <strong>۱۴.۰۰</strong> فعلاً پشتیبانی نمی‌شود<br>
    • پس از جیلبریک از اتصال مستقیم به اینترنت بدون nanoDNS خودداری کنید<br>
    • مسئولیت استفاده بر عهده کاربر است
</div>

</div>

<!-- ===== ADMIN LOGIN ===== -->
<div class="card admin-section" id="admin-login">
    <h2>🔐 پنل مدیریت</h2>
    <input type="password" id="admin-pass" class="admin-input" placeholder="رمز عبور ۳۲ رقمی را وارد کنید...">
    <button onclick="checkAdmin()" class="btn primary" style="width:100%">ورود به پنل</button>
</div>

<!-- ===== ADMIN PANEL (Hidden) ===== -->
<div class="card hidden" id="admin-panel">
    <h2>⚙️ پنل مدیریت — Vortex Play</h2>
    <div style="margin:15px 0">
        <label style="color:#888; font-size:0.9rem;">نام سایت:</label>
        <input type="text" class="admin-input" value="VORTEX PLAY">
        <label style="color:#888; font-size:0.9rem;">لینک اکسپلویت:</label>
        <input type="url" class="admin-input" value="https://jordyidk.github.io/slopkit/">
        <label style="color:#888; font-size:0.9rem;">کانال پشتیبانی:</label>
        <input type="text" class="admin-input" value="@vortexplay3">
    </div>
    <div class="btn-grid">
        <button class="btn primary">✅ ذخیره تغییرات</button>
        <button onclick="toggleAdmin()" class="btn">خروج</button>
    </div>
</div>

<footer>
    <p>پشتیبانی: <a href="#">@vortexplay3</a></p>
    <p style="margin-top:8px; font-size:0.8rem">VORTEX PLAY © ۲۰۲۶ — کلیه حقوق محفوظ است</p>
</footer>

</div>

<script>
// رمز پنل مدیریت
const ADMIN_PASSWORD = 'K9#mP2$xR7!vL3@nQ5&bT1*wZ8%yA4^';

// اضافه کردن خط به لاگ
function addLog(type, text) {
    const console = document.getElementById('log-console');
    const time = new Date().toLocaleTimeString();
    const line = document.createElement('div');
    line.className = `console-line log-${type}`;
    line.textContent = `[${time}] ${text}`;
    console.appendChild(line);
    console.scrollTop = console.scrollHeight;
}

// بررسی رمز مدیریت
function checkAdmin() {
    const pass = document.getElementById('admin-pass').value;
    if (pass === ADMIN_PASSWORD) {
        document.getElementById('admin-login').classList.add('hidden');
        document.getElementById('admin-panel').classList.remove('hidden');
        addLog('success', 'پنل مدیریت فعال شد ✅');
    } else {
        addLog('error', 'رمز عبور نادرست! ❌');
        alert('رمز عبور اشتباه است!');
    }
}

// خروج از پنل
function toggleAdmin() {
    document.getElementById('admin-login').classList.remove('hidden');
    document.getElementById('admin-panel').classList.add('hidden');
    document.getElementById('admin-pass').value = '';
    addLog('info', 'از پنل مدیریت خارج شدید');
}

// نمایش پیام خوش‌آمدگویی پس از بارگذاری
window.onload = function() {
    setTimeout(() => {
        addLog('success', 'Vortex Play v2.5 — سیستم آماده است ✅');
    }, 500);
};
</script>
</body>
</html>
