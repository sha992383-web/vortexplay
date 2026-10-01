<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY | PS5 & PS4 — میزبان‌های تایید شده</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700;900&family=Rajdhani:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#000008;
  --bg1:#03081a;
  --bg2:#081430;
  --p:#7b2fff;
  --c:#00eeff;
  --g:#00ff99;
  --y:#ffcc00;
  --r:#ff3355;
  --t:#e6eeff;
  --d:#6699cc;
  --card:rgba(12,24,56,.7);
  --br:14px;
  --shadow:0 4px 20px rgba(60,20,140,.15);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{
  font-family:'Rajdhani',sans-serif;
  min-height:100vh;color:var(--t);
  background:
    radial-gradient(ellipse at 15% 0%,rgba(123,47,255,.12) 0%,transparent 50%),
    radial-gradient(ellipse at 85% 5%,rgba(0,238,255,.1) 0%,transparent 50%),
    radial-gradient(ellipse at 50% 95%,rgba(0,255,153,.06) 0%,transparent 55%),
    linear-gradient(180deg,var(--bg) 0%,var(--bg1) 45%,var(--bg2) 100%);
  line-height:1.7;padding:14px;overflow-x:hidden
}
body::before{
  content:'';position:fixed;inset:0;
  background-image:
    linear-gradient(rgba(0,238,255,.018) 1px,transparent 1px),
    linear-gradient(90deg,rgba(123,47,255,.018) 1px,transparent 1px);
  background-size:45px 45px;opacity:.35;pointer-events:none;
  animation:gridMove 30s linear infinite
}
@keyframes gridMove{0%{transform:translate(0,0)}100%{transform:translate(45px,45px)}}
.container{max-width:960px;margin:0 auto;position:relative;z-index:1}

/* HEADER */
header{text-align:center;padding:36px 16px 24px}
h1{
  font-family:'Orbitron',sans-serif;
  font-size:clamp(1.9rem,5.5vw,3rem);font-weight:900;letter-spacing:5px;
  background:linear-gradient(135deg,#fff 0%,var(--c) 35%,var(--p) 70%,var(--g) 100%);
  -webkit-background-clip:text;background-clip:text;color:transparent;
  filter:drop-shadow(0 0 16px rgba(0,238,255,.3))
}
.sub{color:#b3ccff;margin-top:8px;font-size:1rem}
.tag{color:var(--g);margin-top:4px;font-size:.9rem}
.stat{
  display:inline-flex;align-items:center;gap:10px;margin-top:18px;
  padding:10px 22px;background:linear-gradient(90deg,rgba(0,255,153,.1),rgba(123,47,255,.08));
  border-radius:50px;border:1px solid rgba(0,255,153,.25)
}
.dot{
  width:11px;height:11px;border-radius:50%;background:var(--g);
  box-shadow:0 0 6px var(--g),0 0 12px var(--g);animation:blink 2s infinite
}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.4}}

/* TABS */
.tabs{display:flex;gap:8px;margin-bottom:18px;flex-wrap:wrap}
.tab{
  flex:1;min-width:110px;padding:12px 14px;border-radius:12px 12px 0 0;
  background:rgba(0,80,160,.12);border:1px solid rgba(0,153,255,.18);
  color:#99ccff;cursor:pointer;font-weight:700;
  font-family:'Orbitron',sans-serif;transition:all .25s ease
}
.tab:hover{background:rgba(0,153,255,.18);color:#fff;border-color:rgba(0,238,255,.4)}
.tab.active{
  background:linear-gradient(180deg,rgba(123,47,255,.2),rgba(0,153,255,.1));
  border-color:var(--p);color:#fff;border-bottom:none
}
.panels{display:none}
.panels.active{display:block;animation:fadeIn .3s ease}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}

/* CARDS */
.card{
  background:var(--card);border-radius:var(--br);padding:22px;
  border:1px solid rgba(0,238,255,.15);margin-bottom:18px;box-shadow:var(--shadow)
}
.card h2{
  font-family:'Orbitron',sans-serif;font-size:1.15rem;margin-bottom:14px;
  display:flex;align-items:center;gap:8px
}
h2.p{color:var(--p)}
h2.c{color:var(--c)}
h2.g{color:var(--g)}
h2.y{color:var(--y)}
h2.r{color:var(--r)}

/* MODEL GRID */
.models{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:12px;margin-bottom:16px}
.model{
  background:rgba(0,60,120,.25);border-radius:12px;padding:14px;
  border-left:3px solid var(--p);transition:transform .2s ease
}
.model:hover{transform:translateX(4px)}
.model h3{font-size:.95rem;color:var(--c);margin-bottom:4px}
.model p{font-size:.85rem;color:var(--d)}
.model.ok{border-left-color:var(--g)}
.model.no{border-left-color:var(--r)}

/* HOST LIST */
.host{
  background:rgba(0,60,120,.2);border-radius:12px;padding:16px;margin-bottom:12px;
  border-left:3px solid var(--c);transition:transform .2s ease
}
.host:hover{transform:translateX(4px)}
.host h3{font-size:.95rem;color:var(--t);margin-bottom:6px}
.host .fw{font-size:.85rem;color:var(--g);margin-bottom:4px}
.host a{
  font-family:'Courier New',monospace;font-size:.85rem;color:var(--c);
  word-break:break-all;text-decoration:none;display:inline-block;
  background:rgba(0,238,255,.08);padding:4px 8px;border-radius:6px;margin:4px 0
}
.host a:hover{background:rgba(0,238,255,.15)}
.host .dev{font-size:.75rem;color:var(--d);margin-top:4px;font-style:italic}

/* TABLE */
table{width:100%;border-collapse:collapse;font-size:.85rem;margin-top:10px}
th,td{padding:10px 12px;text-align:right;border-bottom:1px solid rgba(0,153,255,.12)}
th{color:var(--c);font-family:'Orbitron',sans-serif;font-size:.8rem}
tr:hover{background:rgba(123,47,255,.05)}
.yes{color:var(--g);font-weight:700}
.no{color:var(--r);font-weight:700}
.part{color:var(--y);font-weight:700}

/* DNS BOX */
.dnsgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:10px}
.dnsbox{
  background:rgba(0,60,120,.25);border-radius:10px;padding:14px;
  font-family:'Courier New',monospace;direction:ltr;text-align:left;
  border-right:3px solid var(--g)
}
.dnsbox span{font-size:.75rem;color:var(--d);display:block;margin-bottom:4px}
.dnsbox code{font-size:1rem;color:var(--g)}

/* STEPS */
.steps{counter-reset:step}
.steps p{position:relative;padding-left:36px;margin-bottom:10px}
.steps p::before{
  counter-increment:step;content:counter(step);position:absolute;
  left:0;top:0;width:26px;height:26px;background:var(--p);border-radius:50%;
  display:grid;place-items:center;font-weight:700;font-size:.8rem
}

/* FOOTER */
footer{text-align:center;padding:24px 12px;color:var(--d);font-size:.8rem;margin-top:20px}
</style>
</head>
<body>
<div class="container">

<header>
  <h1>VORTEXPLAY</h1>
  <p class="sub">میزبان‌های تایید شده — PS5 & PS4</p>
  <p class="tag">✅ همه لینک‌ها از منابع رسمی GitHub · SuperPSX · GBAtemp</p>
  <div class="stat"><span class="dot"></span>شبکه فعال — آخرین بروزرسانی: ۱ اکتبر ۲۰۲۶</div>
</header>

<!-- TABS -->
<div class="tabs">
  <button class="tab active" data-tab="ps5">🎮 PS5</button>
  <button class="tab" data-tab="ps4">🕹️ PS4</button>
  <button class="tab" data-tab="dns">📡 DNS مسدودسازی</button>
  <button class="tab" data-tab="guide">📖 راهنما</button>
</div>

<!-- PS5 PANEL -->
<div id="ps5" class="panels active">
  <div class="card">
    <h2 class="p">📋 مدل‌های دستگاه و سازگاری</h2>
    <div class="models">
      <div class="model ok">
        <h3>PS5 Pro</h3>
        <p>CFI-7000 — 7.00 تا 13.60 ✅</p>
      </div>
      <div class="model ok">
        <h3>PS5 Slim Digital</h3>
        <p>CFI-2000 — 7.00 تا 13.60 ✅</p>
      </div>
      <div class="model ok">
        <h3>PS5 Slim با درایو</h3>
        <p>CFI-2000 + CFI-ZDD1 — 7.00 تا 13.60 ✅</p>
      </div>
      <div class="model ok">
        <h3>PS5 نسخه اول (حجیم)</h3>
        <p>CFI-1000/1100/1200 — 7.00 تا 13.60 ✅</p>
      </div>
      <div class="model ok">
        <h3>PS5 Digital نسخه اول</h3>
        <p>CFI-1000B/1100B — 7.00 تا 13.60 ✅</p>
      </div>
      <div class="model no">
        <h3>PS5 — فریم‌ور 14.00+</h3>
        <p>همه مدل‌ها ❌ هنوز پشتیبانی نمی‌شود</p>
      </div>
    </div>
  </div>

  <div class="card">
    <h2 class="c">🔗 میزبان‌های فعال PS5 — فریم‌ور 7.00 تا 13.60</h2>
    
    <div class="host">
      <h3>⭐ Relapse — پیشنهاد قطعی (توسعه‌دهنده: ntfargo)</h3>
      <p class="fw">سازگاری: 7.00 تا 13.60 — شامل PS5 Pro</p>
      <a href="https://ntfargo.github.io/Relapse-Exploit/" target="_blank">https://ntfargo.github.io/Relapse-Exploit/</a>
      <p class="dev">منبع: مخزن رسمی GitHub ntfargo · گزارش SuperPSX</p>
    </div>

    <div class="host">
      <h3>Bagagwa (توسعه‌دهنده: zecoxao)</h3>
      <p class="fw">سازگاری: 7.00 تا 13.60</p>
      <a href="https://zecoxao.github.io/bagagwa/" target="_blank">https://zecoxao.github.io/bagagwa/</a>
      <p class="dev">منبع: GitHub رسمی zecoxao</p>
    </div>

    <div class="host">
      <h3>Poopicker (توسعه‌دهنده: Sonic_Iso)</h3>
      <p class="fw">سازگاری: 7.00 تا 13.60 — رابط ساده</p>
      <a href="https://soniciso1.github.io/poopicker/" target="_blank">https://soniciso1.github.io/poopicker/</a>
      <p class="dev">منبع: GitHub رسمی Sonic_Iso</p>
    </div>

    <div class="host">
      <h3>Y2JB (توسعه‌دهنده: Gezine)</h3>
      <p class="fw">سازگاری: 4.03 تا 12.70 — برای نسخه‌های قدیمی‌تر</p>
      <a href="https://gezine.github.io/y2jb/" target="_blank">https://gezine.github.io/y2jb/</a>
      <p class="dev">منبع: GitHub رسمی Gezine · psXtools.de</p>
    </div>

    <div class="host">
      <h3>Slopkit (توسعه‌دهنده: jordyidk)</h3>
      <p class="fw">سازگاری: 5.00 تا 6.50 — فقط برای Slim/Pro نیاز به BD-JB</p>
      <a href="https://jordyidk.github.io/slopkit/" target="_blank">https://jordyidk.github.io/slopkit/</a>
      <p class="dev">منبع: GitHub رسمی jordyidk · GBAtemp</p>
    </div>

    <div class="host">
      <h3>PSFree (توسعه‌دهنده: TheWizWiki)</h3>
      <p class="fw">سازگاری: 3.00 تا 4.51 — اولین نسخه‌های کنسول</p>
      <a href="https://thewizwiki.github.io/psfree/" target="_blank">https://thewizwiki.github.io/psfree/</a>
      <p class="dev">منبع: صفحه رسمی TheWizWiki · GBAtemp</p>
    </div>
  </div>

  <div class="card">
    <h2 class="g">📊 جدول سازگاری کامل فریم‌ور PS5</h2>
    <table>
      <tr><th>بازه فریم‌ور</th><th>وضعیت</th><th>میزبان پیشنهادی</th></tr>
      <tr><td>3.00 – 4.51</td><td class="yes">✅ کامل</td><td>PSFree</td></tr>
      <tr><td>5.00 – 6.50</td><td class="part">⚠️ محدود</td><td>Slopkit + BD-JB</td></tr>
      <tr><td>7.00 – 12.70</td><td class="yes">✅ کامل</td><td>Relapse / Bagagwa / Y2JB</td></tr>
      <tr><td>13.00 – 13.60</td><td class="yes">✅ کامل — جدیدترین</td><td>Relapse / Bagagwa / Poopicker</td></tr>
      <tr><td>14.00 و بالاتر</td><td class="no">❌ پچ شده</td><td>—</td></tr>
    </table>
  </div>
</div>

<!-- PS4 PANEL -->
<div id="ps4" class="panels">
  <div class="card">
    <h2 class="p">📋 مدل‌های دستگاه و سازگاری</h2>
    <div class="models">
      <div class="model ok">
        <h3>PS4 Pro</h3>
        <p>CUH-70xx / 71xx / 72xx — همه نسخه‌ها ✅</p>
      </div>
      <div class="model ok">
        <h3>PS4 Slim</h3>
        <p>CUH-20xx / 21xx / 22xx — همه نسخه‌ها ✅</p>
      </div>
      <div class="model ok">
        <h3>PS4 نسخه اول (حجیم)</h3>
        <p>CUH-10xx / 11xx / 12xx — همه نسخه‌ها ✅</p>
      </div>
      <div class="model no">
        <h3>PS4 — فریم‌ور 14.00+</h3>
        <p>همه مدل‌ها ❌ هنوز عمومی نشده</p>
      </div>
    </div>
  </div>

  <div class="card">
    <h2 class="c">🔗 میزبان‌های فعال PS4 — فریم‌ور 5.05 تا 13.52</h2>
    
    <div class="host">
      <h3>⭐ Raw13 — پیشنهاد برای 13.02 تا 13.52</h3>
      <p class="fw">سازگاری: 6.72 تا 13.52 · شامل GoldHEN 2.4b18.11</p>
      <a href="https://raw13g.github.io/" target="_blank">https://raw13g.github.io/</a>
      <p class="dev">منبع: SuperPSX · YouTube رسمی</p>
    </div>

    <div class="host">
      <h3>Akela-X v3 — پایدار برای 9.00 تا 13.52</h3>
      <p class="fw">سازگاری: 9.00 تا 13.52 · تست شده در 4PDA</p>
      <a href="https://akela-x.github.io/ps4uhost_v3/" target="_blank">https://akela-x.github.io/ps4uhost_v3/</a>
      <p class="dev">منبع: 4PDA · GitHub رسمی Akela-X</p>
    </div>

    <div class="host">
      <h3>GamerHack — برای 9.00 (PSFree + Lapse)</h3>
      <p class="fw">سازگاری: 9.00 · بدون نیاز به فلش مموری</p>
      <a href="https://gamerhack.github.io/900goldhen_psfree/" target="_blank">https://gamerhack.github.io/900goldhen_psfree/</a>
      <p class="dev">منبع: GitHub رسمی GamerHack</p>
    </div>

    <div class="host">
      <h3>PSX8 — چندمنظوره همه نسخه‌ها</h3>
      <p class="fw">سازگاری: 5.05 تا 13.52 · میزبان جامع</p>
      <a href="https://psx8.github.io/" target="_blank">https://psx8.github.io/</a>
      <p class="dev">منبع: 4PDA · GitHub رسمی</p>
    </div>

    <div class="host">
      <h3>Al-Azif (cthugha) — استاندارد جهانی</h3>
      <p class="fw">سازگاری: 5.05 تا 11.00 · GoldHEN اصلی</p>
      <a href="https://cthugha.exploit.menu/" target="_blank">https://cthugha.exploit.menu/</a>
      <p class="dev">منبع: GBAtemp · SiSTR0 رسمی</p>
    </div>

    <div class="host">
      <h3>Leeful — منوی کامل</h3>
      <p class="fw">سازگاری: 5.05 تا 11.00 · چندین Payload</p>
      <a href="https://leeful.github.io/" target="_blank">https://leeful.github.io/</a>
      <p class="dev">منبع: GBAtemp · GitHub رسمی Leeful</p>
    </div>
  </div>

  <div class="card">
    <h2 class="g">📊 جدول سازگاری کامل فریم‌ور PS4</h2>
    <table>
      <tr><th>بازه فریم‌ور</th><th>وضعیت</th><th>میزبان پیشنهادی</th></tr>
      <tr><td>5.05 / 5.07</td><td class="yes">✅ پایدارترین</td><td>Al-Azif / PSX8</td></tr>
      <tr><td>6.72</td><td class="yes">✅ کامل</td><td>Raw13 / PSX8</td></tr>
      <tr><td>7.00 – 8.52</td><td class="yes">✅ کامل</td><td>PSX8 / GamerHack</td></tr>
      <tr><td>9.00 – 9.60</td><td class="yes">✅ کامل</td><td>GamerHack / Akela-X / Raw13</td></tr>
      <tr><td>10.00 – 11.02</td><td class="yes">✅ کامل</td><td>Al-Azif / Leeful / Raw13</td></tr>
      <tr><td>11.50 – 12.52</td><td class="yes">✅ کامل</td><td>Raw13 / Akela-X</td></tr>
      <tr><td>13.02 – 13.52</td><td class="yes">✅ جدیدترین</td><td>Raw13 / Akela-X</td></tr>
      <tr><td>14.00 و بالاتر</td><td class="no">❌ عمومی نشده</td><td>—</td></tr>
    </table>
  </div>
</div>

<!-- DNS PANEL -->
<div id="dns" class="panels">
  <div class="card">
    <h2 class="g">📡 DNS مسدودسازی آپدیت خودکار</h2>
    <p style="margin-bottom:14px">این مقادیر را در تنظیمات شبکه کنسول وارد کنید تا از آپدیت ناخواسته جلوگیری شود:</p>
    
    <div class="dnsgrid">
      <div class="dnsbox">
        <span>DNS اصلی — Relapse</span>
        <code>45.56.67.85</code>
      </div>
      <div class="dnsbox">
        <span>DNS جایگزین — Al-Azif</span>
        <code>165.227.83.145</code>
      </div>
      <div class="dnsbox">
        <span>DNS سوم — Nomadic</span>
        <code>62.210.38.117</code>
      </div>
      <div class="dnsbox">
        <span>DNS چهارم — دوم</span>
        <code>192.241.221.79</code>
      </div>
    </div>
    
    <div class="note-box" style="margin-top:16px;background:rgba(255,204,0,.08);border-right:3px solid var(--y);padding:12px;border-radius:10px">
      <strong>💡 نکته مهم:</strong> پس از تنظیم DNS، گزینه «اتصال اینترنت» را یک بار خاموش و روشن کنید تا مقادیر اعمال شوند. در PS5 از «راهنمای کاربری» و در PS4 از «مرورگر اینترنت» استفاده نمایید.
    </div>
  </div>
</div>

<!-- GUIDE PANEL -->
<div id="guide" class="panels">
  <div class="card">
    <h2 class="y">📖 راهنمای گام‌به‌گام</h2>
    <div class="steps">
      <p><strong>بررسی فریم‌ور:</strong> تنظیمات → سیستم → اطلاعات سیستم → شماره نسخه را یادداشت کنید. اگر ۱۴.۰۰ یا بالاتر است، هنوز کار نمی‌کند ❌</p>
      <p><strong>غیرفعال‌سازی آپدیت:</strong> تنظیمات → سیستم → آپدیت خودکار → غیرفعال کردن دریافت و نصب خودکار ✅</p>
      <p><strong>تنظیم DNS:</strong> تنظیمات → شبکه → تنظیمات پیشرفته → DNS دستی → مقادیر بالا را وارد کنید ✅</p>
      <p><strong>باز کردن میزبان:</strong> در PS5: تنظیمات → راهنمای کاربری → لینک را وارد کنید. در PS4: مرورگر → لینک را وارد کنید ✅</p>
      <p><strong>اجرای اکسپلویت:</strong> صفحه بارگذاری می‌شود → منتظر بمانید (گاهی ۲-۳ بار تلاش لازم است) → پیام موفقیت ظاهر می‌شود ✅</p>
      <p><strong>بارگذاری GoldHEN / HEN:</strong> پس از موفقیت، منو ظاهر می‌شود → گزینه مربوط به فعال‌سازی را انتخاب کنید → منتظر بمانید تا کنسول ری‌استارت یا منو باز شود ✅</p>
      <p><strong>نصب بازی‌ها:</strong> تنظیمات → اشکال‌زدایی → نصب بسته → فایل PKG را از حافظه خارجی انتخاب و نصب کنید ✅</p>
      <p><strong>توجه:</strong> این روش «موقت» است — پس از هر بار خاموش و روشن کردن کنسول، مراحل ۴ تا ۶ را تکرار کنید ✅</p>
    </div>
  </div>
</div>

<footer>
  VORTEXPLAY · میزبان‌های تایید شده · منابع: GitHub رسمی توسعه‌دهندگان · SuperPSX · GBAtemp · 4PDA · GAMERGEN<br>
  ⚠️ مسئولیت استفاده با کاربر است · هرگز به PSN متصل نشوید تا از مسدودسازی جلوگیری کنید
</footer>

</div>

<script>
// تب‌ها — بدون لگ
const tabs=document.querySelectorAll('.tab');
const panels=document.querySelectorAll('.panels');
tabs.forEach(tab=>{
  tab.addEventListener('click',()=>{
    const id=tab.dataset.tab;
    tabs.forEach(t=>t.classList.remove('active'));
    panels.forEach(p=>p.classList.remove('active'));
    tab.classList.add('active');
    document.getElementById(id).classList.add('active');
  });
});
</script>
</body>
</html>
