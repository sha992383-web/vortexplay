<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
<title>VORTEXPLAY | Relapse — PS4 & PS5 Ultimate Host</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&family=Rajdhani:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
    --cyber-black: #000208;
    --cyber-deep: #020a1f;
    --cyber-mid: #051533;
    --cyber-blue: #0099ff;
    --cyber-cyan: #00eeff;
    --cyber-sky: #66ffff;
    --cyber-electric: #00ccff;
    --cyber-purple: #5566ff;
    --cyber-red: #ff3366;
    --cyber-green: #00ff99;
    --cyber-gold: #ffcc00;
    --text-bright: #e0f7ff;
    --text-mid: #80ccff;
    --text-dim: #3377bb;
    --glow-blue: 0 0 10px rgba(0,153,255,.6), 0 0 20px rgba(0,153,255,.4), 0 0 40px rgba(0,153,255,.2);
    --glow-cyan: 0 0 10px rgba(0,238,255,.6), 0 0 20px rgba(0,238,255,.4), 0 0 40px rgba(0,238,255,.2);
    --glow-green: 0 0 10px rgba(0,255,153,.6), 0 0 20px rgba(0,255,153,.4);
    --glow-red: 0 0 10px rgba(255,51,102,.6), 0 0 20px rgba(255,51,102,.4);
}
* { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
body {
    background: 
        radial-gradient(ellipse at top left, rgba(0,153,255,.15) 0%, transparent 50%),
        radial-gradient(ellipse at top right, rgba(85,102,255,.12) 0%, transparent 50%),
        radial-gradient(ellipse at bottom center, rgba(0,238,255,.08) 0%, transparent 60%),
        linear-gradient(180deg, #000208 0%, #020a1f 40%, #051533 100%);
    min-height: 100vh; color: var(--text-mid); line-height: 1.8; padding: 20px 15px; overflow-x: hidden;
}
body::before {
    content: ''; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background-image: 
        linear-gradient(rgba(0,153,255,.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,153,255,.03) 1px, transparent 1px);
    background-size: 40px 40px; pointer-events: none; opacity: .5;
    animation: gridFlow 25s linear infinite;
}
body::after {
    content: ''; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: repeating-linear-gradient(transparent, transparent 2px, rgba(0,238,255,.02) 2px, rgba(0,238,255,.02) 4px);
    pointer-events: none; animation: scan 4s linear infinite; opacity: .3;
}
@keyframes gridFlow {
    0% { transform: translate(0, 0); }
    100% { transform: translate(40px, 40px); }
}
@keyframes scan {
    0% { transform: translateY(-100%); }
    100% { transform: translateY(100%); }
}
.container { max-width: 960px; margin: 0 auto; position: relative; z-index: 1; }

/* ===== HEADER ===== */
header { text-align: center; padding: 50px 20px 40px; position: relative; }
.logo-container { position: relative; display: inline-block; }
.logo-ring {
    position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
    width: 110%; height: 140%; border-radius: 50%;
    border: 1px solid rgba(0,238,255,.3);
    animation: ringPulse 3s ease-in-out infinite;
}
.logo-ring:nth-child(2) { animation-delay: -.75s; opacity: .6; }
.logo-ring:nth-child(3) { animation-delay: -1.5s; opacity: .3; }
@keyframes ringPulse {
    0% { transform: translate(-50%, -50%) scale(1); opacity: .3; }
    50% { transform: translate(-50%, -50%) scale(1.15); opacity: .6; }
    100% { transform: translate(-50%, -50%) scale(1); opacity: .3; }
}
.logo {
    font-family: 'Orbitron', sans-serif; font-size: 3.2rem; font-weight: 800; letter-spacing: 6px;
    background: linear-gradient(135deg, #ffffff, #66ffff, #0099ff, #5566ff, #00eeff);
    background-size: 300% 300%; animation: logoShift 5s ease infinite;
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    position: relative; z-index: 1;
    text-shadow: none; filter: drop-shadow(0 0 15px rgba(0,238,255,.4));
}
@keyframes logoShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
.subtitle {
    color: var(--text-bright); margin-top: 15px; font-size: 1.2rem; font-weight: 500;
    text-shadow: 0 0 20px rgba(0,238,255,.3); font-family: 'Orbitron', sans-serif; letter-spacing: 2px;
}
.tagline {
    color: var(--cyber-green); margin-top: 8px; font-size: .95rem; letter-spacing: 1px;
    text-shadow: 0 0 10px rgba(0,255,153,.4);
}
.status-bar {
    display: inline-flex; align-items: center; gap: 12px; margin-top: 25px;
    background: linear-gradient(90deg, rgba(0,255,153,.1), rgba(0,153,255,.08));
    padding: 12px 30px; border-radius: 50px; border: 1px solid rgba(0,255,153,.3);
    box-shadow: var(--glow-green), inset 0 0 15px rgba(0,255,153,.05);
    backdrop-filter: blur(10px);
}
.status-dot {
    width: 14px; height: 14px; background: var(--cyber-green); border-radius: 50%;
    box-shadow: 0 0 8px var(--cyber-green), 0 0 16px var(--cyber-green);
    animation: statusBlink 2s infinite;
}
@keyframes statusBlink {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: .4; transform: scale(.8); }
}
.status-text { color: var(--text-bright); font-weight: 600; font-size: 1rem; }

/* ===== TABS ===== */
.tabs { display: flex; gap: 10px; margin-bottom: 20px; }
.tab {
    flex: 1; padding: 16px; border: 1px solid rgba(0,153,255,.2);
    background: rgba(0,50,100,.15); color: var(--text-mid);
    border-radius: 14px 14px 0 0; cursor: pointer; text-align: center;
    font-weight: 700; transition: all .3s ease; font-family: 'Orbitron', sans-serif; letter-spacing: 1px;
}
.tab:hover { background: rgba(0,153,255,.15); border-color: rgba(0,153,255,.4); }
.tab.active {
    background: linear-gradient(180deg, rgba(0,153,255,.25), rgba(0,100,200,.15));
    border-color: var(--cyber-cyan); color: white; border-bottom: none;
    box-shadow: 0 -5px 20px rgba(0,238,255,.15);
}
.tab.ps4-tab.active { border-color: var(--cyber-blue); }
.tab.ps5-tab.active { border-color: var(--cyber-purple); }
.tab-content { display: none; animation: fadeUp .4s ease; }
.tab-content.active { display: block; }
@keyframes fadeUp {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
}

/* ===== CARDS ===== */
.card {
    background: linear-gradient(135deg, rgba(5,25,60,.7), rgba(2,10,30,.85));
    border-radius: 20px; padding: 30px; margin-bottom: 24px;
    border: 1px solid rgba(0,153,255,.2);
    box-shadow: 0 8px 32px rgba(0,50,120,.15), inset 0 1px 0 rgba(255,255,255,.05);
    backdrop-filter: blur(12px); position: relative; overflow: hidden;
    transition: all .35s ease;
}
.card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--cyber-cyan), transparent);
    opacity: 0; transition: opacity .3s;
}
.card:hover {
    border-color: rgba(0,238,255,.4); transform: translateY(-4px);
    box-shadow: 0 12px 48px rgba(0,80,160,.25);
}
.card:hover::before { opacity: 1; }
.card.ps4 { border-color: rgba(0,153,255,.3); }
.card.ps4::before { background: linear-gradient(90deg, transparent, var(--cyber-blue), transparent); }
.card.ps5 { border-color: rgba(85,102,255,.35); }
.card.ps5::before { background: linear-gradient(90deg, transparent, var(--cyber-purple), transparent); }
.card h2 {
    font-family: 'Orbitron', sans-serif; font-size: 1.35rem; margin-bottom: 18px;
    display: flex; align-items: center; gap: 12px; font-weight: 700; letter-spacing: 1px;
}
.card.ps4 h2 { color: var(--cyber-blue); text-shadow: 0 0 15px rgba(0,153,255,.3); }
.card.ps5 h2 { color: var(--cyber-purple); text-shadow: 0 0 15px rgba(85,102,255,.3); }
.card p { margin-bottom: 14px; color: var(--text-mid); font-size: 1rem; }

/* ===== DNS BOX ===== */
.dns-box {
    background: linear-gradient(135deg, rgba(0,60,120,.35), rgba(0,30,80,.45));
    border-radius: 14px; padding: 24px 28px;
    font-family: 'Courier New', monospace; font-size: 1.15rem; margin: 20px 0;
    border-right: 4px solid var(--cyber-cyan);
    box-shadow: inset 0 0 25px rgba(0,238,255,.1);
    direction: ltr; text-align: left;
}
.dns-label { color: var(--text-dim); font-size: .9rem; margin-bottom: 8px; display: block; }
.dns-value {
    color: var(--cyber-sky); font-weight: 700; font-size: 1.3rem;
    text-shadow: 0 0 12px rgba(0,238,255,.5);
}

/* ===== BUTTONS ===== */
.btn-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 14px; margin-top: 18px; }
.btn {
    background: linear-gradient(135deg, rgba(0,100,200,.35), rgba(0,60,140,.25));
    border: 1px solid rgba(0,153,255,.35); border-radius: 14px;
    padding: 20px 22px; color: var(--text-bright); font-size: 1rem; font-weight: 600;
    cursor: pointer; transition: all .3s ease; text-align: center; text-decoration: none; display: inline-block;
    position: relative; overflow: hidden; font-family: 'Orbitron', sans-serif; letter-spacing: .5px;
}
.btn::after {
    content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,.15), transparent);
    transition: left .5s ease;
}
.btn:hover::after { left: 100%; }
.btn:hover {
    transform: translateY(-3px) scale(1.02);
    box-shadow: 0 10px 30px rgba(0,153,255,.25);
}
.btn.primary {
    background: linear-gradient(135deg, #0099ff, #0066cc); border: none; color: white; font-weight: 800;
    box-shadow: 0 6px 25px rgba(0,153,255,.4);
}
.btn.primary:hover {
    background: linear-gradient(135deg, #00aaff, #0077dd);
    box-shadow: 0 10px 35px rgba(0,153,255,.5);
}
.btn.relapse {
    background: linear-gradient(135deg, #5566ff, #3344cc); border: none; color: white; font-weight: 800;
    box-shadow: 0 6px 25px rgba(85,102,255,.4);
}
.btn.relapse:hover {
    background: linear-gradient(135deg, #6677ff, #4455dd);
    box-shadow: 0 10px 35px rgba(85,102,255,.5);
}
.btn-icon { font-size: 1.5rem; margin-bottom: 6px; display: block; }
.btn-main { font-size: 1.1rem; padding: 22px; }

/* ===== LISTS & BADGES ===== */
.fw-list { list-style: none; margin-top: 12px; }
.fw-list li {
    padding: 12px 0; border-bottom: 1px solid rgba(0,153,255,.1);
    display: flex; align-items: center; gap: 10px; flex-wrap: wrap;
}
.badge {
    display: inline-block; padding: 4px 12px; border-radius: 20px; font-size: .8rem; font-weight: 700;
    margin-left: auto; font-family: 'Orbitron', sans-serif;
}
.badge.full { background: rgba(0,255,153,.15); color: #00ff99; border: 1px solid rgba(0,255,153,.3); box-shadow: 0 0 8px rgba(0,255,153,.2); }
.badge.partial { background: rgba(255,204,0,.15); color: #ffcc00; border: 1px solid rgba(255,204,0,.3); box-shadow: 0 0 8px rgba(255,204,0,.2); }
.badge.none { background: rgba(255,51,102,.15); color: #ff3366; border: 1px solid rgba(255,51,102,.3); box-shadow: 0 0 8px rgba(255,51,102,.2); }
.badge.new { background: rgba(85,102,255,.2); color: #aabbff; border: 1px solid rgba(85,102,255,.4); animation: pulseBadge 2s infinite; }
@keyframes pulseBadge {
    0%, 100% { box-shadow: 0 0 5px rgba(85,102,255,.3); }
    50% { box-shadow: 0 0 15px rgba(85,102,255,.6); }
}

/* ===== INFO BOXES ===== */
.info-box {
    background: linear-gradient(135deg, rgba(0,153,255,.08), rgba(0,80,160,.06));
    border: 1px solid rgba(0,153,255,.2); border-radius: 14px;
    padding: 20px 24px; margin-top: 18px; color: #b0e7ff;
    border-left: 3px solid var(--cyber-cyan);
}
.warn-box {
    background: linear-gradient(135deg, rgba(255,51,102,.1), rgba(120,30,60,.08));
    border: 1px solid rgba(255,51,102,.25); border-radius: 14px;
    padding: 22px 26px; margin-top: 24px; color: #ffc8d0;
    border-left: 3px solid var(--cyber-red);
}
.highlight { color: var(--cyber-sky); font-weight: 700; }
.highlight-green { color: var(--cyber-green); font-weight: 700; }
.highlight-purple { color: var(--cyber-purple); font-weight: 700; }
.highlight-red { color: var(--cyber-red); font-weight: 700; }

/* ===== FOOTER ===== */
footer {
    text-align: center; margin-top: 60px; padding: 30px 20px;
    color: var(--text-dim); font-size: .85rem;
    border-top: 1px solid rgba(0,153,255,.15);
}
footer a { color: var(--cyber-cyan); text-decoration: none; }
footer .update-note { margin-top: 10px; font-size: .78rem; color: #2a5a9a; }

/* ===== RESPONSIVE ===== */
@media (max-width: 600px) {
    .logo { font-size: 2rem; letter-spacing: 2px; }
    .card { padding: 22px 18px; }
    .btn-grid { grid-template-columns: 1fr; }
    .tabs { flex-direction: column; gap: 5px; }
    .tab { border-radius: 12px; }
}
</style>
</head>
<body>
<div class="container">

<header>
    <div class="logo-container">
        <div class="logo-ring"></div>
        <div class="logo-ring"></div>
        <div class="logo-ring"></div>
        <h1 class="logo">VORTEXPLAY</h1>
    </div>
    <p class="subtitle">RELOAPSE — PS4 & PS5 ULTIMATE HOST</p>
    <p class="tagline">🔥 PS5 تا نسخه <span class="highlight-green">13.60</span> | PS4 تا نسخه <span class="highlight-green">13.52</span> — بدون فیلترشکن</p>
    <div class="status-bar">
        <span class="status-dot"></span>
        <span class="status-text">میزبان Relapse فعال — منتشر شده ۳۰ سپتامبر ۲۰۲۶</span>
    </div>
</header>

<!-- DNS SECTION -->
<div class="card">
    <h2>📡 گام صفر: تنظیم DNS — قطع آپدیت خودکار</h2>
    <p>قبل از باز کردن هر صفحه‌ای، اینترنت کنسول را با این تنظیمات پیکربندی کنید:</p>
    <div class="dns-box">
        <span class="dns-label">DNS اصلی (Primary):</span>
        <span class="dns-value">45.56.67.85</span><br><br>
        <span class="dns-label">DNS فرعی (Secondary):</span>
        <span style="color:#4a7acc">— خالی بگذارید —</span>
    </div>
    <div class="info-box">
        💡 این DNS رسمی پروژه Relapse است ← ارتباط با سرورهای آپدیت سونی را مسدود می‌کند تا کنسول به نسخه ۱۴.۰۰ آپدیت نشود.
    </div>
</div>

<!-- TABS -->
<div class="tabs">
    <div class="tab ps4-tab active" onclick="switchTab('ps4')">🎮 PlayStation 4</div>
    <div class="tab ps5-tab" onclick="switchTab('ps5')">🎮 PlayStation 5 — Relapse 13.60</div>
</div>

<!-- ================================= PS4 SECTION ================================ -->
<div id="ps4" class="tab-content active">
    <div class="card ps4">
        <h2>⚡ میزبان اصلی PS4 — همه نسخه‌ها</h2>
        <p>مرورگر اینترنت PS4 را باز کرده و روی دکمه بزنید:</p>
        <div class="btn-grid" style="margin-top:20px">
            <a href="https://raw13g.github.io" target="_blank" class="btn primary btn-main">
                <span class="btn-icon">👑</span> میزبان اصلی — 5.05 تا 13.52
            </a>
            <a href="https://salt-12.github.io/main/index.html" target="_blank" class="btn">
                <span class="btn-icon">🔄</span> میزبان جایگزین
            </a>
        </div>
        <p style="margin-top:15px;font-size:.9rem;color:#4a7acc">
            شامل: 5.05 / 6.72 / 7.02 / 7.55 / 9.00 / 11.00 / 11.50 / 12.00 / 12.52 / 13.00 / 13.52
        </p>
    </div>

    <div class="card ps4">
        <h2>📋 لیست کامل سازگاری PS4</h2>
        <ul class="fw-list">
            <li><strong>5.05</strong> — GoldHEN پایدار <span class="badge full">کامل</span></li>
            <li><strong>6.71 / 6.72</strong> — GoldHEN پایدار <span class="badge full">کامل</span></li>
            <li><strong>7.01 / 7.02</strong> — GoldHEN <span class="badge full">کامل</span></li>
            <li><strong>7.50 / 7.51 / 7.55</strong> — GoldHEN <span class="badge full">کامل</span></li>
            <li><strong>8.00 / 8.01 / 8.03</strong> — از طریق 9.00 <span class="badge full">موجود</span></li>
            <li><strong>9.00 / 9.03 / 9.04 / 9.50 / 9.60</strong> — GoldHEN + PSFree <span class="badge full">پیشنهادی</span></li>
            <li><strong>10.00 تا 10.71</strong> — GoldHEN <span class="badge full">کامل</span></li>
            <li><strong>11.00 / 11.02 / 11.50 / 11.52</strong> — WebKit جدید <span class="badge full">کامل</span></li>
            <li><strong>12.00 / 12.02 / 12.03 / 12.09 / 12.50 / 12.52</strong> — فعال <span class="badge full">کامل</span></li>
            <li><strong>13.00 / 13.02 / 13.04 / 13.50 / 13.52</strong> — PSFree + GoldHEN v2.4 <span class="badge new">جدید</span></li>
            <li><strong>14.00 و بالاتر</strong> — هنوز منتشر نشده <span class="badge none">پشتیبانی نمی‌شود</span></li>
        </ul>
    </div>

    <div class="card ps4">
        <h2>📦 مراحل کامل کار</h2>
        <div style="line-height:2.3;margin-top:10px">
            <p><strong>۱)</strong> تنظیمات DNS بالا را در اینترنت PS4 وارد کنید ← جلوگیری از آپدیت</p>
            <p><strong>۲)</strong> مرورگر اینترنت را باز کرده → لینک میزبان را وارد کنید</p>
            <p><strong>۳)</strong> صفحه بارگذاری شد → منتظر اجرای خودکار بمانید (ممکن است چند بار نیاز باشد)</p>
            <p><strong>۴)</strong> منو ظاهر شد → گزینه <strong>GoldHEN</strong> را انتخاب کنید</p>
            <p><strong>۵)</strong> پس از فعال شدن → بازی‌ها، برنامه‌ها و پلاگین‌ها را نصب کنید</p>
            <p style="color:#ffcc00;margin-top:10px">⚠️ هر بار خاموش/روشن کردن کنسول، مراحل را تکرار کنید (موقت است)</p>
        </div>
    </div>
</div>

<!-- ================================= PS5 SECTION ================================ -->
<div id="ps5" class="tab-content">
    <div class="card ps5">
        <h2>⚡ میزبان Relapse — 7.00 تا 13.60 <span class="badge new">جدید</span></h2>
        <p>راهنمای کاربری (User Guide) PS5 را باز کرده و روی دکمه بزنید:</p>
        <div class="btn-grid" style="margin-top:20px">
            <a href="https://ntfargo.github.io/Relapse-Exploit/" target="_blank" class="btn relapse btn-main">
                <span class="btn-icon">💜</span> Relapse — 7.00 تا 13.60
            </a>
            <a href="https://thewizwikii.github.io/psfree" target="_blank" class="btn">
                <span class="btn-icon">🔓</span> PSFree — 3.00 تا 4.51
            </a>
            <a href="https://jordyidk.github.io/slopkit/" target="_blank" class="btn">
                <span class="btn-icon">⚡</span> Slopkit — 5.00 تا 6.50
            </a>
            <a href="https://gezine.github.io/y2jb/" target="_blank" class="btn">
                <span class="btn-icon">🔧</span> Y2JB — 4.03 تا 12.70
            </a>
        </div>
        <div class="info-box" style="margin-top:18px">
            � پروژه Relapse در تاریخ ۳۰ سپتامبر ۲۰۲۶ منتشر شد ← از ۷.۰۰ تا ۱۳.۶۰ را پوشش می‌دهد ← شامل PS5 Pro هم می‌شود ✅
        </div>
    </div>

    <div class="card ps5">
        <h2>📋 لیست کامل سازگاری PS5</h2>
        <ul class="fw-list">
            <li><strong>3.00 تا 3.60</strong> — PSFree + etaHEN <span class="badge full">پایدار</span></li>
            <li><strong>4.00 تا 4.51</strong> — PSFree + kstuff + etaHEN <span class="badge full">پایدار</span></li>
            <li><strong>5.00 تا 5.50</strong> — Slopkit / BD-JB <span class="badge partial">محدود</span></li>
            <li><strong>6.00 تا 6.50</strong> — Slopkit + کیت‌های کمکی <span class="badge partial">محدود</span></li>
            <li><strong>7.00 تا 12.70</strong> — Relapse + Y2JB <span class="badge full">کامل</span></li>
            <li><strong>13.00 تا 13.60</strong> — <span class="highlight-green">Relapse</span> <span class="badge new">تازه منتشر شده</span></li>
            <li><strong>14.00 و بالاتر</strong> — سونی در ۱۶ سپتامبر ۲۰۲۶ بلاک کرد <span class="badge none">پشتیبانی نمی‌شود</span></li>
        </ul>
    </div>

    <div class="card ps5">
        <h2>📦 مراحل کامل Relapse (7.00 تا 13.60)</h2>
        <div style="line-height:2.3;margin-top:10px">
            <p><strong>۱)</strong> DNS: <code style="background:rgba(0,153,255,.2);padding:2px 8px;border-radius:4px">45.56.67.85</code> را در تنظیمات اینترنت وارد کنید</p>
            <p><strong>۲)</strong> سیستم → راهنمای کاربری را باز کنید</p>
            <p><strong>۳)</strong> نوار آدرس را فعال کرده → لینک میزبان Relapse را وارد کنید</p>
            <p><strong>۴)</strong> منتظر بمانید → مرحله اول WebKit اجرا می‌شود (ممکن است چند بار نیاز باشد)</p>
            <p><strong>۵)</strong> موفق شد → مرحله دوم کرنل اجرا می‌شود (کمی صبر کنید)</p>
            <p><strong>۶)</strong> پیام موفقیت ظاهر شد → حالا می‌توانید از طریق پورت ۹۰۲۱ Payload ارسال کنید</p>
            <p><strong>۷)</strong> یا مستقیماً در همان صفحه → kstuff-lite → ShadowMountPlus → etaHEN را بارگذاری کنید</p>
            <p><strong>۸)</strong> در آخر → nanoDNS را اجرا کنید تا آپدیت برای همیشه مسدود بماند</p>
            <p style="color:#ffcc00;margin-top:10px">⚠️ Relapse موقت است → هر بار خاموش/روشن کردن باید تکرار شود</p>
        </div>
    </div>

    <div class="card ps5">
        <h2>🔧 Payloadهای پیشنهادی پس از Relapse</h2>
        <ul style="line-height:2.2;margin-top:10px">
            <li><strong>kstuff-lite.elf</strong> ← دسترسی کامل سیستم + فعال‌سازی کپی خور</li>
            <li><strong>ShadowMountPlus.elf</strong> ← نصب بازی‌های بکاپ و فایل‌های pkg</li>
            <li><strong>etaHEN.elf</strong> ← محیط هوم‌برو + اجرای برنامه‌های غیررسمی</li>
            <li><strong>nanoDNS.elf</strong> ← مسدودسازی دائمی سرورهای آپدیت سونی</li>
        </ul>
    </div>
</div>

<!-- WARNINGS -->
<div class="warn-box">
    ⚠️ <strong>هشدارهای حیاتی:</strong><br><br>
    • <span class="highlight-red">هیچ‌گاه</span> اجازه ندهید کنسول به طور خودکار آپدیت شود ← حتی اتصال لحظه‌ای کافی است<br>
    • نسخه ۱۴.۰۰ سونی در ۱۶ سپتامبر ۲۰۲۶ منتشر شد ← Relapse را بلاک کرده است ⛔<br>
    • پس از جیلبریک، از ورود به PSN خودداری کنید ← ریسک مسدود شدن دائمی وجود دارد<br>
    • Relapse ممکن است در برخی تلاش‌ها منجر به فریز یا ریبوت کنسول شود ← طبیعی است، دوباره تلاش کنید<br>
    • تمام میزبان‌ها از گیت‌هاب هستند ← بدون فیلترشکن در ایران باز می‌شوند ✅<br>
    • مسئولیت استفاده و عواقب احتمالی بر عهده کاربر است
</div>

<footer>
    <p><strong>VORTEXPLAY — Relapse Unified Host System</strong></p>
    <p style="margin-top:8px">منابع: ntfargo/Relapse-Exploit · raw13g · TheWizWiki · Gezine/Y2JB · Jordy/Slopkit</p>
    <p class="update-note">آخرین به‌روزرسانی: ۱ مهر ۱۴۰۵ — PS5 تا 13.60 | PS4 تا 13.52 | PS5 Pro سازگار ✅</p>
</footer>

</div>

<script>
function switchTab(console) {
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
    if (console === 'ps4') {
        document.querySelector('.tab.ps4-tab').classList.add('active');
        document.getElementById('ps4').classList.add('active');
    } else {
        document.querySelector('.tab.ps5-tab').classList.add('active');
        document.getElementById('ps5').classList.add('active');
    }
}
</script>
</body>
</html>
