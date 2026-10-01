<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate">
<title>VORTEXPLAY | PS5 & PS4 Ultimate Hosts — Official Verified Sources</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&family=Rajdhani:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<style>
:root {
    --vtx-black: #000005;
    --vtx-deep: #020510;
    --vtx-mid: #05102a;
    --vtx-blue: #0099ff;
    --vtx-cyan: #00eeff;
    --vtx-sky: #66ffff;
    --vtx-purple: #7b2fff;
    --vtx-violet: #b040ff;
    --vtx-green: #00ff99;
    --vtx-red: #ff2255;
    --vtx-gold: #ffcc00;
    --text-bright: #f0f7ff;
    --text-mid: #99ccff;
    --text-dim: #3366aa;
    --glow-cyan: 0 0 8px rgba(0,238,255,.7), 0 0 16px rgba(0,238,255,.4), 0 0 32px rgba(0,238,255,.2);
    --glow-purple: 0 0 8px rgba(123,47,255,.7), 0 0 16px rgba(123,47,255,.4), 0 0 32px rgba(123,47,255,.2);
    --glow-green: 0 0 8px rgba(0,255,153,.7), 0 0 16px rgba(0,255,153,.4);
    --glow-gold: 0 0 8px rgba(255,204,0,.5), 0 0 16px rgba(255,204,0,.3);
}
* { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
body {
    background: 
        radial-gradient(ellipse at 20% 0%, rgba(0,153,255,.18) 0%, transparent 55%),
        radial-gradient(ellipse at 80% 10%, rgba(123,47,255,.15) 0%, transparent 50%),
        radial-gradient(ellipse at 50% 90%, rgba(0,255,153,.08) 0%, transparent 60%),
        linear-gradient(180deg, #000005 0%, #020510 35%, #05102a 100%);
    min-height: 100vh; color: var(--text-mid); line-height: 1.85; padding: 20px 15px; overflow-x: hidden;
}
body::before {
    content: ''; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background-image: 
        linear-gradient(rgba(0,238,255,.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,153,255,.025) 1px, transparent 1px);
    background-size: 35px 35px; opacity: .5; pointer-events: none;
    animation: gridMove 30s linear infinite;
}
body::after {
    content: ''; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: linear-gradient(transparent 0%, rgba(0,238,255,.015) 50%, transparent 100%);
    pointer-events: none; animation: scanLine 4s linear infinite; opacity: .25;
}
@keyframes gridMove {
    0% { transform: translate(0, 0); }
    100% { transform: translate(35px, 35px); }
}
@keyframes scanLine {
    0% { transform: translateY(-100%); }
    100% { transform: translateY(100%); }
}
.container { max-width: 980px; margin: 0 auto; position: relative; z-index: 1; }

/* ===== HEADER ===== */
header { text-align: center; padding: 50px 20px 35px; position: relative; }
.logo-wrapper { position: relative; display: inline-block; }
.logo-ring {
    position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
    border-radius: 50%; border: 1px solid rgba(0,238,255,.3);
    animation: ringPulse 3s ease-in-out infinite;
}
.logo-ring:nth-child(1) { width: 115%; height: 145%; animation-delay: 0s; }
.logo-ring:nth-child(2) { width: 130%; height: 170%; animation-delay: -0.75s; opacity: .5; }
.logo-ring:nth-child(3) { width: 145%; height: 195%; animation-delay: -1.5s; opacity: .25; }
@keyframes ringPulse {
    0% { transform: translate(-50%, -50%) scale(1); opacity: .3; }
    50% { transform: translate(-50%, -50%) scale(1.15); opacity: .6; }
    100% { transform: translate(-50%, -50%) scale(1); opacity: .3; }
}
.logo {
    font-family: 'Orbitron', sans-serif; font-size: 3.4rem; font-weight: 900; letter-spacing: 8px;
    background: linear-gradient(135deg, #ffffff, #66ffff, #0099ff, #7b2fff, #b040ff, #00ff99);
    background-size: 400% 400%; animation: logoFlow 6s ease infinite;
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    position: relative; z-index: 1;
    filter: drop-shadow(0 0 20px rgba(0,238,255,.45));
}
@keyframes logoFlow {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
.subtitle {
    color: var(--text-bright); margin-top: 15px; font-size: 1.2rem;
    font-family: 'Orbitron', sans-serif; letter-spacing: 3px;
    text-shadow: 0 0 15px rgba(123,47,255,.4);
}
.tagline {
    color: var(--vtx-green); margin-top: 8px; font-size: .95rem;
    text-shadow: 0 0 10px rgba(0,255,153,.4);
}
.status-bar {
    display: inline-flex; align-items: center; gap: 12px; margin-top: 25px;
    background: linear-gradient(90deg, rgba(0,255,153,.12), rgba(0,153,255,.08), rgba(123,47,255,.08));
    padding: 14px 30px; border-radius: 50px;
    border: 1px solid rgba(0,255,153,.3);
    box-shadow: var(--glow-green), inset 0 0 20px rgba(0,255,153,.05);
    backdrop-filter: blur(10px);
}
.status-dot {
    width: 14px; height: 14px; background: var(--vtx-green); border-radius: 50%;
    box-shadow: 0 0 8px var(--vtx-green), 0 0 16px var(--vtx-green);
    animation: statusBlink 2s infinite;
}
@keyframes statusBlink {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: .4; transform: scale(.8); }
}
.status-text { color: var(--text-bright); font-weight: 600; font-size: 1rem; }

/* ===== DNS SECTION ===== */
.dns-card {
    background: linear-gradient(135deg, rgba(8,20,50,.75), rgba(3,8,25,.85));
    border-radius: 20px; padding: 28px; margin-bottom: 24px;
    border: 1px solid rgba(0,255,153,.25);
    box-shadow: 0 0 25px rgba(0,255,153,.1);
    position: relative; overflow: hidden;
}
.dns-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--vtx-green), transparent);
}
.dns-card h2 {
    color: var(--vtx-green); margin-bottom: 18px; font-size: 1.35rem;
    font-family: 'Orbitron', sans-serif; display: flex; align-items: center; gap: 10px;
}
.dns-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 15px; }
.dns-box {
    background: rgba(0,60,120,.3); border-radius: 14px; padding: 20px;
    font-family: 'Courier New', monospace; direction: ltr; text-align: left;
    border-right: 3px solid var(--vtx-cyan);
    box-shadow: inset 0 0 15px rgba(0,238,255,.08);
}
.dns-label { color: var(--text-dim); font-size: .85rem; margin-bottom: 8px; display: block; }
.dns-ip {
    color: var(--vtx-sky); font-weight: 700; font-size: 1.25rem;
    text-shadow: 0 0 10px rgba(0,238,255,.5);
}

/* ===== TABS ===== */
.tabs { display: flex; gap: 10px; margin-bottom: 20px; }
.tab {
    flex: 1; padding: 16px; border: 1px solid rgba(0,153,255,.2);
    background: rgba(0,80,160,.12); color: var(--text-mid);
    border-radius: 14px 14px 0 0; cursor: pointer; text-align: center;
    font-weight: 700; transition: all .3s ease;
    font-family: 'Orbitron', sans-serif; letter-spacing: 1px;
}
.tab:hover {
    background: rgba(0,153,255,.18); border-color: rgba(0,238,255,.4);
    color: var(--text-bright);
}
.tab.active {
    background: linear-gradient(180deg, rgba(123,47,255,.2), rgba(0,153,255,.12));
    border-color: var(--vtx-violet); color: white; border-bottom: none;
    box-shadow: 0 -5px 20px rgba(176,64,255,.15);
}
.tab-content { display: none; animation: fadeInUp .45s ease; }
.tab-content.active { display: block; }
@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
}

/* ===== CARDS ===== */
.card {
    background: linear-gradient(135deg, rgba(6,18,45,.75), rgba(2,8,22,.88));
    border-radius: 20px; padding: 30px; margin-bottom: 24px;
    border: 1px solid rgba(123,47,255,.2);
    box-shadow: 0 8px 32px rgba(50,20,120,.15);
    position: relative; overflow: hidden; transition: all .35s ease;
}
.card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--vtx-purple), var(--vtx-cyan), transparent);
    opacity: 0; transition: opacity .3s;
}
.card:hover {
    border-color: rgba(176,64,255,.4); transform: translateY(-4px);
    box-shadow: 0 14px 48px rgba(80,30,180,.25);
}
.card:hover::before { opacity: 1; }
.card h2 {
    font-size: 1.35rem; margin-bottom: 20px; display: flex; align-items: center; gap: 12px;
    font-family: 'Orbitron', sans-serif; letter-spacing: 1px;
}
.card.primary h2 { color: var(--vtx-violet); text-shadow: 0 0 15px rgba(176,64,255,.3); }
.card.secondary h2 { color: var(--vtx-cyan); text-shadow: 0 0 15px rgba(0,238,255,.3); }
.card.accent h2 { color: var(--vtx-green); text-shadow: 0 0 15px rgba(0,255,153,.3); }

/* ===== HOST ITEMS ===== */
.host-list { display: flex; flex-direction: column; gap: 14px; margin-top: 18px; }
.host-item {
    background: rgba(0,80,160,.15); border-radius: 14px; padding: 20px;
    border: 1px solid rgba(0,153,255,.15); transition: all .3s ease;
}
.host-item:hover {
    border-color: rgba(176,64,255,.4); background: rgba(80,30,180,.12);
    transform: translateX(-5px);
}
.host-top { display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 10px; margin-bottom: 10px; }
.host-name { font-weight: 700; font-size: 1.05rem; color: var(--text-bright); }
.host-badge {
    padding: 5px 14px; border-radius: 20px; font-size: .75rem; font-weight: 700;
    font-family: 'Orbitron', sans-serif; letter-spacing: .5px;
}
.badge-main { background: rgba(176,64,255,.2); color: #ddbbff; border: 1px solid rgba(176,64,255,.4); box-shadow: 0 0 8px rgba(176,64,255,.2); animation: badgePulse 2.5s infinite; }
.badge-new { background: rgba(0,255,153,.15); color: #88ffcc; border: 1px solid rgba(0,255,153,.3); }
.badge-alt { background: rgba(0,153,255,.15); color: #88ccff; border: 1px solid rgba(0,153,255,.3); }
.badge-classic { background: rgba(255,204,0,.12); color: #ffdd66; border: 1px solid rgba(255,204,0,.25); }
.badge-verified { background: rgba(0,200,100,.15); color: #66ffaa; border: 1px solid rgba(0,200,100,.3); }
.badge-source { background: rgba(100,100,255,.12); color: #aaccff; border: 1px solid rgba(100,100,255,.25); font-size: .7rem; }
@keyframes badgePulse {
    0%, 100% { box-shadow: 0 0 5px rgba(176,64,255,.2); }
    50% { box-shadow: 0 0 15px rgba(176,64,255,.5); }
}
.host-link {
    font-family: 'Courier New', monospace; font-size: .9rem;
    color: var(--vtx-sky); word-break: break-all; margin: 8px 0;
}
.host-link a { color: var(--vtx-cyan); text-decoration: none; transition: color .2s; }
.host-link a:hover { color: var(--vtx-violet); text-shadow: 0 0 8px rgba(176,64,255,.5); }
.host-info { font-size: .85rem; color: var(--text-dim); line-height: 1.7; margin-top: 5px; }
.host-info strong { color: var(--vtx-green); }
.host-source { margin-top: 6px; font-size: .75rem; color: #4466aa; font-style: italic; }

/* ===== BUTTONS ===== */
.btn-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 14px; margin-top: 20px; }
.btn {
    display: block; text-align: center; padding: 20px 24px; border-radius: 14px;
    font-weight: 700; font-size: 1rem; text-decoration: none;
    font-family: 'Orbitron', sans-serif; letter-spacing: 1px;
    transition: all .3s ease; position: relative; overflow: hidden;
}
.btn::after {
    content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,.15), transparent);
    transition: left .6s ease;
}
.btn:hover::after { left: 100%; }
.btn-main {
    background: linear-gradient(135deg, #7b2fff, #5511dd);
    color: white; border: none; box-shadow: 0 6px 25px rgba(123,47,255,.4);
    font-size: 1.1rem; padding: 24px;
}
.btn-main:hover {
    transform: translateY(-3px) scale(1.02);
    box-shadow: 0 12px 35px rgba(123,47,255,.5);
}
.btn-alt {
    background: linear-gradient(135deg, rgba(0,238,255,.15), rgba(0,153,255,.1));
    color: var(--vtx-sky); border: 1px solid rgba(0,238,255,.3);
}
.btn-alt:hover {
    border-color: rgba(0,238,255,.6); background: rgba(0,238,255,.15);
    transform: translateY(-2px);
}
.btn-icon { font-size: 1.5rem; margin-bottom: 6px; display: block; }

/* ===== INFO & WARNING BOXES ===== */
.info-box {
    background: rgba(0,153,255,.07); border-left: 3px solid var(--vtx-cyan);
    padding: 20px; border-radius: 0 12px 12px 0; margin-top: 18px;
    color: #b0e7ff;
}
.warn-box {
    background: rgba(255,34,85,.08); border-left: 3px solid var(--vtx-red);
    padding: 22px; border-radius: 0 12px 12px 0; margin-top: 24px;
    color: #ffc8d0;
}
.note-box {
    background: rgba(255,204,0,.07); border-left: 3px solid var(--vtx-gold);
    padding: 20px; border-radius: 0 12px 12px 0; margin-top: 18px;
    color: #fff0c0;
}
.highlight { font-weight: 700; }
.highlight-purple { color: var(--vtx-violet); }
.highlight-green { color: var(--vtx-green); }
.highlight-cyan { color: var(--vtx-cyan); }
.highlight-red { color: var(--vtx-red); }
.highlight-gold { color: var(--vtx-gold); }

/* ===== FIRMWARE COMPATIBILITY TABLE ===== */
.fw-table {
    width: 100%; border-collapse: collapse; margin-top: 15px; font-size: .9rem;
}
.fw-table th, .fw-table td {
    padding: 12px 15px; text-align: right; border-bottom: 1px solid rgba(0,153,255,.15);
}
.fw-table th { color: var(--vtx-cyan); font-family: 'Orbitron', sans-serif; font-size: .85rem; letter-spacing: .5px; }
.fw-table tr:hover { background: rgba(123,47,255,.05); }
.status-yes { color: var(--vtx-green); font-weight: 700; }
.status-no { color: var(--vtx-red); font-weight: 700; }
.status-partial { color: var(--vtx-gold); font-weight: 700; }

/* ===== FOOTER ===== */
footer {
    text-align: center; margin-top: 60px; padding: 30px 20px;
    color: var(--text-dim); font-size: .8rem;
    border-top: 1px solid rgba(12,47,255,.15);
}
footer a { color: var(--vtx-cyan); text-decoration: none; }
footer .sources { margin-top: 10px; font-size: .75rem; color: #2a5a9a; line-height: 1.6; }

/* ===== RESPONSIVE ===== */
@media (max-width: 600px) {
    .logo { font-size: 2rem; letter-spacing: 3px; }
    .card { padding: 22px 18px; }
    .tabs { flex-direction: column; gap: 5px; }
    .tab { border-radius: 12px; }
    .fw-table { font-size: .8rem; }
    .fw-table th, .fw-table td { padding: 10px 8px; }
}
</style>
</head>
<body>
<div class="container">

<header>
    <div class="logo-wrapper">
        <div class="logo-ring"></div>
        <div class="logo-ring"></div>
        <div class="logo-ring"></div>
        <h1 class="logo">VORTEXPLAY</h1>
    </div>
    <p class="subtitle">OFFICIAL VERIFIED HOST NETWORK — PS5 13.60 & PS4 13.52</p>
    <p class="tagline">✅ همه لینک‌ها از منابع معتبر: GitHub رسمی · SuperPSX · GBAtemp · 4PDA — بدون فیلترشکن</p>
    <div class="status-bar">
        <span class="status-dot"></span>
        <span class="status-text">شبکه فعال — آخرین به‌روزرسانی: ۱ مهر ۱۴۰۵ / ۱ اکتبر ۲۰۲۶</span>
    </div>
</header>

<!-- DNS SECTION -->
<div class="dns-card">
    <h2>📡 گام اول: تنظیم DNS — قطع کامل آپدیت خودکار سونی</h2>
    <p style="margin-bottom:18px">قبل از باز کردن هرگونه صفحه اکسپلویت، حتماً این تنظیمات را در کنسول اعمال کنید تا از اتصال خودکار به سرورهای سونی و آپدیت ناخواسته جلوگیری شود:</p>
    <div class="dns-grid">
        <div class="dns-box">
            <span class="dns-label">DNS اصلی — پیشنهادی Relapse</span>
            <span class="dns-ip">45.56.67.85</span>
        </div>
        <div class="dns-box">
            <span class="dns-label">DNS جایگزین — Al-Azif (معروف‌ترین)</span>
            <span class="dns-ip">165.227.83.145</span>
        </div>
        <div class="dns-box">
            <span class="dns-label">DNS دوم جایگزین</span>
            <span class="dns-ip">192.241.221.79</span>
        </div>
        <div class="dns-box">
            <span class="dns-label">DNS سوم — Nomadic</span>
            <span class="dns-ip">62.210.38.117</span>
        </div>
    </div>
    <p style="margin-top:15px;font-size:.85rem;color:#4a7acc">✅ در PS5: تنظیمات → شبکه → تنظیمات اتصال → پیشرفته → DNS دستی → مقادیر بالا را وارد کنید<br>✅ DNS دوم را می‌توانید خالی بگذارید یا از مقادیر جایگزین استفاده کنید</p>
</div>

<!-- TABS -->
<div class="tabs">
    <div class="tab active" onclick="switchTab('ps5')">🎮 PS5 — تا نسخه 13.60</div>
    <div class="tab" onclick="switchTab('ps4')">🎮 PS4 — تا نسخه 13.52</div>
    <div class="tab" onclick="switchTab('guide')">📖 راهنمای کامل</div>
</div>

<!-- ================================= PS5 SECTION ================================= -->
<div id="ps5" class="tab-content active">
    <!-- COMPATIBILITY TABLE -->
    <div class="card accent">
        <h2>📋 جدول سازگاری فریم‌ور PS5</h2>
        <table class="fw-table">
            <thead>
                <tr>
                    <th>بازه نسخه فریم‌ور</th>
                    <th>وضعیت پشتیبانی</th>
                    <th>میزبان پیشنهادی</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>3.00 تا 4.51</td>
                    <td class="status-yes">✅ پشتیبانی کامل</td>
                    <td>PSFree</td>
                </tr>
                <tr>
                    <td>5.00 تا 6.50</td>
                    <td class="status-partial">⚠️ پشتیبانی محدود</td>
                    <td>Slopkit</td>
                </tr>
                <tr>
                    <td>7.00 تا 12.70</td>
                    <td class="status-yes">✅ پشتیبانی کامل</td>
                    <td>Relapse / Bagagwa / Y2JB</td>
                </tr>
                <tr>
                    <td>13.00 تا 13.60</td>
                    <td class="status-yes">✅ پشتیبانی کامل — جدیدترین</td>
                    <td>Relapse / Poopicker / Bagagwa</td>
                </tr>
                <tr>
                    <td>14.00 و بالاتر</td>
                    <td class="status-no">❌ هنوز پشتیبانی نمی‌شود</td>
                    <td>—</td>
                </tr>
            </tbody>
        </table>
    </div>

    <!-- MAIN HOST -->
    <div class="card primary">
        <h2>👑 میزبان اصلی — Relapse (توصیه قطعی)</h2>
        <p>این میزبان رسمی‌ترین و اصلی‌ترین منبع اکسپلویت Relapse است که توسط ntfargo و تیم مشارکت‌کننده منتشر شده و از طریق منابع معتبر جهانی تایید گردیده است. برای استفاده، وارد «راهنمای کاربری» PS5 شده و لینک زیر را در نوار آدرس وارد نمایید:</p>
        
        <div class="btn-grid" style="margin-top:22px">
            <a href="https://ntfargo.github.io/Relapse-Exploit/" target="_blank" class="btn btn-main">
                <span class="btn-icon">🚀</span>
                RELAPSE — 7.00 تا 13.60
            </a>
        </div>

        <div class="host-list" style="margin-top:25px">
            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Relapse — توسعه‌دهنده: ntfargo & تیم</span>
                    <span class="host-badge badge-main">اصلی · رسمی</span>
                </div>
                <div class="host-link"><a href="https://ntfargo.github.io/Relapse-Exploit/" target="_blank">https://ntfargo.github.io/Relapse-Exploit/</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS5 7.00 تا 13.60</strong> — شامل PS5 Pro<br>
                    ✅ منتشر شده: ۳۰ سپتامبر ۲۰۲۶ / ۹ مهر ۱۴۰۵<br>
                    ✅ مجوز: MIT — متن‌باز و عمومی<br>
                    ✅ شامل: WebKit + Kernel Exploit + بارگذاری Payload از پورت ۹۰۲۱<br>
                    ✅ بدون نیاز به فایل خارجی — کامل درون‌مرورگری<br>
                    ✅ منبع: مخزن رسمی GitHub ntfargo / گزارش SuperPSX
                </div>
                <div class="host-source">منبع مرجع: SuperPSX · GitHub رسمی ntfargo</div>
            </div>
        </div>
    </div>

    <!-- ALTERNATIVE HOSTS GROUP 1: 13.x COMPATIBLE -->
    <div class="card secondary">
        <h2>🔄 میزبان‌های جایگزین سازگار با 13.60</h2>
        <p>در صورت عدم پاسخگویی میزبان اصلی، از این گزینه‌های تایید شده استفاده کنید. همه این‌ها از یک اکسپلویت مشترک استفاده می‌کنند و نتیجه یکسانی دارند:</p>
        
        <div class="host-list">
            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Bagagwa — توسعه‌دهنده: zecoxao</span>
                    <span class="host-badge badge-verified">جایگزین تایید شده</span>
                </div>
                <div class="host-link"><a href="https://zecoxao.github.io/bagagwa/" target="_blank">https://zecoxao.github.io/bagagwa/</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS5 7.00 تا 13.60</strong><br>
                    ✅ توسعه‌دهنده: zecoxao — از اعضای شناخته‌شده جامعه<br>
                    ✅ منبع: مخزن رسمی GitHub zecoxao
                </div>
                <div class="host-source">منبع مرجع: GitHub رسمی zecoxao</div>
            </div>

            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Poopicker — توسعه‌دهنده: Sonic_Iso</span>
                    <span class="host-badge badge-verified">جایگزین تایید شده</span>
                </div>
                <div class="host-link"><a href="https://soniciso1.github.io/poopicker/" target="_blank">https://soniciso1.github.io/poopicker/</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS5 7.00 تا 13.60</strong><br>
                    ✅ رابط کاربری ساده و مبتنی بر انتخاب<br>
                    ✅ منبع: مخزن رسمی GitHub Sonic_Iso
                </div>
                <div class="host-source">منبع مرجع: GitHub رسمی Sonic_Iso</div>
            </div>
        </div>
    </div>

    <!-- OLDER FIRMWARE HOSTS -->
    <div class="card secondary">
        <h2>📌 میزبان‌های نسخه‌های قدیمی‌تر PS5</h2>
        <p>اگر فریم‌ور کنسول شما پایین‌تر از ۷.۰۰ است، از این میزبان‌های اختصاصی استفاده کنید:</p>
        
        <div class="host-list">
            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Y2JB — توسعه‌دهنده: Gezine</span>
                    <span class="host-badge badge-alt">پایدار</span>
                </div>
                <div class="host-link"><a href="https://gezine.github.io/y2jb/" target="_blank">https://gezine.github.io/y2jb/</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS5 4.03 تا 12.70</strong><br>
                    ✅ برای کنسول‌هایی که هنوز آپدیت نشده‌اند<br>
                    ✅ منبع: مخزن رسمی GitHub Gezine
                </div>
                <div class="host-source">منبع مرجع: GitHub رسمی Gezine · psXtools.de</div>
            </div>

            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">PSFree — توسعه‌دهنده: TheWizWiki</span>
                    <span class="host-badge badge-classic">قدیمی</span>
                </div>
                <div class="host-link"><a href="https://thewizwikii.github.io/psfree" target="_blank">https://thewizwikii.github.io/psfree</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS5 3.00 تا 4.51</strong><br>
                    ✅ برای اولین نسخه‌های عرضه شده کنسول<br>
                    ✅ شامل etaHEN + k-stuff<br>
                    ✅ منبع: صفحه رسمی TheWizWiki
                </div>
                <div class="host-source">منبع مرجع: صفحه رسمی TheWizWiki · GBAtemp</div>
            </div>

            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Slopkit — توسعه‌دهنده: jordyidk</span>
                    <span class="host-badge badge-classic">محدود</span>
                </div>
                <div class="host-link"><a href="https://jordyidk.github.io/slopkit/" target="_blank">https://jordyidk.github.io/slopkit/</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS5 5.00 تا 6.50</strong><br>
                    ✅ برای کنسول‌های با فریم‌ور میانی<br>
                    ✅ منبع: مخزن رسمی GitHub jordyidk
                </div>
                <div class="host-source">منبع مرجع: GitHub رسمی jordyidk</div>
            </div>
        </div>
    </div>

    <!-- STEPS PS5 -->
    <div class="card accent">
        <h2>📋 مراحل کامل کار با Relapse — گام‌به‌گام</h2>
        <div style="line-height:2.4;margin-top:10px">
            <p><strong>گام ۱ — بررسی فریم‌ور:</strong> تنظیمات → سیستم → اطلاعات سیستم → شماره نسخه را یادداشت کنید. اگر ۱۴.۰۰ یا بالاتر است، هنوز هیچ روشی کار نمی‌کند ❌</p>
            <p><strong>گام ۲ — غیرفعال‌سازی آپدیت خودکار:</strong> تنظیمات → سیستم → آپدیت سیستم → گزینه‌های آپدیت → دریافت خودکار و نصب خودکار را غیرفعال کنید ✅</p>
            <p><strong>گام ۳ — تنظیم DNS:</strong> تنظیمات → شبکه → اتصال اینترنت → تنظیمات پیشرفته → DNS دستی → مقدار <code style="background:rgba(0,255,153,.2);padding:3px 10px;border-radius:4px">45.56.67.85</code> را وارد کنید ✅</p>
            <p><strong>گام ۴ — باز کردن راهنمای کاربری:</strong> تنظیمات → راهنمای کاربری و سلامت/ایمنی → راهنمای کاربری را باز کنید ✅</p>
            <p><strong>گام ۵ — وارد کردن لینک:</strong> در نوار آدرس مرورگر، لینک <code style="background:rgba(0,238,255,.2);padding:3px 10px;border-radius:4px">https://ntfargo.github.io/Relapse-Exploit/</code> را وارد و منتظر بمانید ✅</p>
            <p><strong>گام ۶ — اجرای اکسپلویت:</strong> صفحه بارگذاری می‌شود → چند ثانیه صبر کنید → پیام موفقیت‌آمیز بودن WebKit ظاهر می‌شود → سپس اکسپلویت کرنل اجرا می‌شود ✅</p>
            <p><strong>گام ۷ — دریافت پورت ۹۰۲۱:</strong> در صورت موفقیت، صفحه پورت <code style="background:rgba(176,64,255,.2);padding:3px 10px;border-radius:4px">9021</code> را نمایش می‌دهد → این یعنی آماده دریافت Payload است ✅</p>
            <p><strong>گام ۸ — ارسال Payload:</strong> از نرم‌افزارهای ارسال‌کننده مانند Universal Payload Manager یا Payload Sender استفاده کنید و این‌ها را به ترتیب ارسال کنید: k-stuff-lite → ShadowMountPlus → etaHEN ✅</p>
            <p><strong>گام ۹ — نهایی‌سازی:</strong> پس از بارگذاری etaHEN، به منوی اصلی بازگردید → اکنون تنظیمات اشکال‌زدایی فعال است → می‌توانید فایل‌های PKG را نصب کنید ✅</p>
            <p><strong>گام ۱۰ — مسدودسازی دائمی آپدیت:</strong> در آخرین مرحله، Payload مربوط به مسدودسازی DNS را اجرا کنید تا پس از هر بار روشن ماندن کنسول، ارتباط با سرورهای سونی قطع بماند ✅</p>
            <p style="color:#ffcc00;margin-top:15px">⚠️ نکته مهم: Relapse موقت است — پس از هر بار خاموش و روشن کردن کنسول، باید مراحل بالا را تکرار کنید. این موضوع تا زمانی که نسخه دائمی یا مبتنی بر سخت‌افزار عرضه نشده، طبیعی است.</p>
        </div>
    </div>
</div>

<!-- ================================= PS4 SECTION ================================= -->
<div id="ps4" class="tab-content">
    <!-- PS4 COMPATIBILITY -->
    <div class="card accent">
        <h2>📋 جدول سازگاری فریم‌ور PS4</h2>
        <table class="fw-table">
            <thead>
                <tr>
                    <th>بازه نسخه فریم‌ور</th>
                    <th>وضعیت پشتیبانی</th>
                    <th>میزبان پیشنهادی</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>5.05 / 5.07</td>
                    <td class="status-yes">✅ پشتیبانی کامل — پایدارترین</td>
                    <td>Al-Azif / Leeful</td>
                </tr>
                <tr>
                    <td>6.72</td>
                    <td class="status-yes">✅ پشتیبانی کامل</td>
                    <td>Al-Azif / Raw13 / Akela-X</td>
                </tr>
                <tr>
                    <td>7.0x تا 9.00</td>
                    <td class="status-yes">✅ پشتیبانی کامل</td>
                    <td>Al-Azif / Leeful / Akela-X</td>
                </tr>
                <tr>
                    <td>9.03 تا 11.00</td>
                    <td class="status-yes">✅ پشتیبانی کامل</td>
                    <td>Al-Azif / Raw13</td>
                </tr>
                <tr>
                    <td>11.50 تا 12.00</td>
                    <td class="status-yes">✅ پشتیبانی کامل</td>
                    <td>Raw13 / Akela-X</td>
                </tr>
                <tr>
                    <td>13.02 تا 13.52</td>
                    <td class="status-yes">✅ جدیدترین — منتشر شده ۱۹ سپتامبر</td>
                    <td>Raw13 / Akela-X</td>
                </tr>
                <tr>
                    <td>14.00 و بالاتر</td>
                    <td class="status-no">❌ هنوز پشتیبانی نمی‌شود</td>
                    <td>—</td>
                </tr>
            </tbody>
        </table>
    </div>

    <!-- PS4 MAIN HOSTS -->
    <div class="card primary">
        <h2>👑 میزبان‌های اصلی PS4 — تا 13.52</h2>
        
        <div class="host-list">
            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Raw13 — پیشنهادی برای 13.02 تا 13.52</span>
                    <span class="host-badge badge-main">جدیدترین</span>
                </div>
                <div class="host-link"><a href="https://raw13g.github.io" target="_blank">https://raw13g.github.io</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS4 6.72 تا 13.52</strong> — شامل جدیدترین نسخه ۱۳.۵۲<br>
                    ✅ منتشر شده: ۱۹–۲۰ سپتامبر ۲۰۲۶<br>
                    ✅ شامل: PSFree + GoldHEN v2.4b18.11 + ابزارهای تکمیلی<br>
                    ✅ منبع: SuperPSX · جامعه جهانی کپی‌خور
                </div>
                <div class="host-source">منبع مرجع: SuperPSX · گزارش‌های تایید شده کاربران</div>
            </div>

            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Akela-X — میزبان پایدار</span>
                    <span class="host-badge badge-verified">تایید شده</span>
                </div>
                <div class="host-link"><a href="https://akela-x.github.io/ps4uhost_v3/" target="_blank">https://akela-x.github.io/ps4uhost_v3/</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS4 9.00 تا 13.52</strong><br>
                    ✅ تست شده در انجمن 4PDA — بسیار پایدار<br>
                    ✅ منبع: صفحه رسمی Akela در GitHub
                </div>
                <div class="host-source">منبع مرجع: 4PDA · GitHub رسمی Akela-X</div>
            </div>

            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Al-Azif cthugha — مرجع جهانی</span>
                    <span class="host-badge badge-classic">معروف‌ترین</span>
                </div>
                <div class="host-link"><a href="https://cthugha.exploit.menu" target="_blank">https://cthugha.exploit.menu</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS4 5.05 تا 11.00</strong> — استاندارد جهانی<br>
                    ✅ توسعه‌دهنده: SiSTR0 — سازنده اصلی GoldHEN<br>
                    ✅ DNS مرجع: 165.227.83.145 / 192.241.221.79<br>
                    ✅ منبع: GBAtemp · GAMERGEN
                </div>
                <div class="host-source">منبع مرجع: GBAtemp · GAMERGEN · رسمی SiSTR0</div>
            </div>

            <div class="host-item">
                <div class="host-top">
                    <span class="host-name">Leeful — منوی کامل</span>
                    <span class="host-badge badge-alt">پایدار</span>
                </div>
                <div class="host-link"><a href="https://leeful.github.io" target="_blank">https://leeful.github.io</a></div>
                <div class="host-info">
                    ✅ سازگاری: <strong>PS4 5.05 تا 11.00</strong><br>
                    ✅ شامل: منوی کامل + چندین Payload + ابزارهای کمکی<br>
                    ✅ منبع: GBAtemp · صفحه رسمی Leeful
                </div>
                <div class="host-source">منبع مرجع: GBAtemp · GitHub رسمی Leeful</div>
            </div>
        </div>
    </div>

    <!-- PS4 STEPS -->
    <div class="card accent">
        <h2>📋 مراحل کامل کار با PS4 — گام‌به‌گام</h2>
        <div style="line-height:2.4">
            <p><strong>گام ۱ — بررسی فریم‌ور:</strong> تنظیمات → سیستم → اطلاعات سیستم → شماره نسخه را بررسی کنید. اگر ۱۴.۰۰ یا بالاتر است، کار نمی‌کند ❌</p>
            <p><strong>گام ۲ — غیرفعال‌سازی آپدیت:</strong> تنظیمات → سیستم → آپدیت خودکار → غیرفعال کنید ✅</p>
            <p><strong>گام ۳ — تنظیم DNS:</strong> تنظیمات → شبکه → ا
