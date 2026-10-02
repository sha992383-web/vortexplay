<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>VORTEXPLAY | مرکز جامع جیلبریک PS4 & PS5</title>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{height:100%;scroll-behavior:smooth}
:root{
  --primary:#00d4ff;--secondary:#00ff96;--accent:#ff2d55;
  --dark:#050510;--card:rgba(10,25,50,.75);--border:rgba(0,212,255,.25);
  --text:#e6f1ff;--muted:#8ab4d6;--success:#00ff96;--warn:#ffc107;--danger:#ff4466
}
body{
  font-family:'Vazirmatn',sans-serif;
  background:
    radial-gradient(ellipse at 15% 0%,rgba(0,212,255,.18)0%,transparent 50%),
    radial-gradient(ellipse at 85% 5%,rgba(0,255,150,.12)0%,transparent 50%),
    radial-gradient(circle at 50% 100%,rgba(0,100,200,.08)0%,transparent 60%),
    linear-gradient(180deg,var(--dark)0%,#0a1628 40%,#0f1f3a 100%);
  color:var(--text);min-height:100vh;padding:14px 12px;line-height:1.8
}
.container{max-width:760px;margin:0 auto}
header{text-align:center;margin-bottom:28px;padding:25px 15px 20px;position:relative}
header::before{
  content:'';position:absolute;top:0;left:50%;transform:translateX(-50%);
  width:120px;height:4px;background:linear-gradient(90deg,var(--primary),var(--secondary));border-radius:2px
}
h1{
  font-size:2rem;font-weight:900;letter-spacing:-.5px;
  background:linear-gradient(135deg,var(--primary),var(--secondary));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  margin-bottom:8px
}
.subtitle{color:var(--muted);font-size:.95rem;max-width:500px;margin:0 auto}
.badge{display:inline-flex;align-items:center;gap:6px;padding:6px 14px;border-radius:50px;font-size:.78rem;font-weight:700}
.badge.ok{background:rgba(0,255,150,.15);color:var(--success);border:1px solid rgba(0,255,150,.25)}
.badge.warn{background:rgba(255,193,7,.15);color:var(--warn);border:1px solid rgba(255,193,7,.25)}
.badge.no{background:rgba(255,68,102,.15);color:var(--danger);border:1px solid rgba(255,68,102,.25)}
.card{
  background:var(--card);border-radius:24px;padding:26px 22px;margin-bottom:18px;
  border:1px solid var(--border);backdrop-filter:blur(12px);
  box-shadow:0 8px 32px rgba(0,100,200,.08)
}
h2{font-size:1.2rem;color:var(--primary);margin-bottom:18px;display:flex;align-items:center;gap:10px;font-weight:800}
h3{font-size:1rem;color:var(--secondary);margin:20px 0 10px;font-weight:700}
.alert{border-radius:14px;padding:16px 18px;margin-bottom:16px}
.alert.danger{background:rgba(255,68,102,.1);border:1px solid rgba(255,68,102,.25);color:#ffb3c2}
.alert.info{background:rgba(0,212,255,.1);border:1px solid rgba(0,212,255,.25);color:#99ddff}
.alert.success{background:rgba(0,255,150,.1);border:1px solid rgba(0,255,150,.25);color:#b3ffd9}
.alert.note{background:rgba(255,193,7,.08);border-left:3px solid var(--warn);color:#ffd780}
.version-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:10px;margin:14px 0}
.version-tag{padding:12px 10px;border-radius:12px;text-align:center;font-weight:700;font-size:.85rem}
.version-tag.ok{background:rgba(0,255,150,.12);border:1px solid rgba(0,255,150,.25);color:var(--success)}
.version-tag.no{background:rgba(255,68,102,.12);border:1px solid rgba(255,68,102,.25);color:var(--danger)}
.btn{
  display:inline-flex;align-items:center;justify-content:center;gap:8px;
  padding:15px 22px;border-radius:14px;border:none;font-weight:700;font-size:.95rem;
  cursor:pointer;transition:.25s all;text-decoration:none;font-family:inherit;width:100%;margin:8px 0
}
.btn-primary{background:linear-gradient(135deg,var(--primary),var(--secondary));color:#000;font-weight:800;box-shadow:0 6px 20px rgba(0,212,255,.25)}
.btn-primary:active{transform:scale(.97)}
.btn-copy{background:rgba(0,212,255,.18);border:1px solid rgba(0,212,255,.3);color:var(--primary);padding:10px 16px;border-radius:10px;margin-top:10px;cursor:pointer;font-size:.85rem;font-weight:600}
.link-box{
  background:rgba(0,0,0,.45);padding:14px 16px;border-radius:12px;direction:ltr;text-align:left;
  overflow-x:auto;margin:10px 0;font-size:.85rem;color:var(--secondary);word-break:break-all;
  font-family:'Courier New',monospace;line-height:1.6
}
.step{margin:16px 0;padding-right:12px;border-right:3px solid rgba(0,212,255,.3)}
.step-num{display:inline-flex;align-items:center;justify-content:center;width:32px;height:32px;border-radius:50%;background:rgba(0,212,255,.25);color:var(--primary);font-weight:900;margin-left:10px;font-size:.9rem;flex-shrink:0}
.step-row{display:flex;align-items:flex-start;gap:12px;margin-bottom:14px}
ul{padding-right:5px;margin:12px 0}
li{margin:8px 0}
strong{color:var(--secondary)}
.tab-wrap{display:flex;gap:10px;margin-bottom:20px;position:sticky;top:0;z-index:10;background:rgba(5,5,16,.9);padding:8px;border-radius:16px;backdrop-filter:blur(10px)}
.tab{flex:1;padding:12px 10px;border-radius:12px;border:none;background:transparent;color:var(--muted);cursor:pointer;font-weight:700;font-size:.9rem;transition:.2s}
.tab.active{background:linear-gradient(135deg,var(--primary),var(--secondary));color:#000}
.tab-content{display:none;animation:fadeIn .3s ease}
.tab-content.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
.host-table{width:100%;border-collapse:separate;border-spacing:6px;margin:14px 0}
.host-table th,.host-table td{padding:12px 10px;text-align:right;border-radius:10px;font-size:.85rem}
.host-table th{background:rgba(0,212,255,.15);color:var(--primary);font-weight:800}
.host-table td{background:rgba(255,255,255,.03)}
.check-yes{color:var(--success);font-weight:900}
.check-no{color:var(--danger);font-weight:900}
footer{text-align:center;margin-top:30px;padding:20px;color:var(--muted);font-size:.8rem;border-top:1px solid rgba(255,255,255,.05)}
.spacer{height:8px}
</style>
</head>
<body>
<div class="container">
  <header>
    <h1>⚡ VORTEXPLAY</h1>
    <p class="subtitle">مرکز جامع و تخصصی جیلبریک و کپی‌خور کنسول‌های بازی — PS4 & PS5<br>تمام میزبان‌ها بدون نیاز به فیلترشکن در ایران کار می‌کنند ✅</p>
  </header>

  <div class="alert danger">
    ⚠️ <strong>هشدار مهم و حیاتی:</strong> هرگز کنسول را به اینترنت رسمی سونی متصل نکنید. قبل از هر کاری، به‌روزرسانی خودکار سیستم را کاملاً غیرفعال نمایید. مسئولیت هرگونه مسدودی حساب یا کنسول با کاربر است. این سایت صرفاً جنبه آموزشی و اطلاع‌رسانی دارد.
  </div>

  <!-- تب‌های اصلی -->
  <div class="tab-wrap">
    <button class="tab active" onclick="switchTab('ps5')">🎮 پلی‌استیشن ۵</button>
    <button class="tab" onclick="switchTab('ps4')">🕹 پلی‌استیشن ۴</button>
    <button class="tab" onclick="switchTab('faq')">📘 سؤالات رایج</button>
  </div>

  <!-- ================================== PS5 ================================== -->
  <div id="ps5" class="tab-content active">
    <div class="card">
      <h2>✅ وضعیت سازگاری فریمور</h2>
      <p style="margin-bottom:12px">اکسپلویت <strong>Relapse</strong> که توسط توسعه‌دهنده <em>ntfargo</em> منتشر شد، از تاریخ ۹ مهر ۱۴۰۵ (۲۹ سپتامبر ۲۰۲۶) به‌صورت عمومی در دسترس قرار گرفته و از نسخه ۷.۰۰ تا ۱۳.۶۰ را پشتیبانی می‌کند.</p>
      <div class="version-grid">
        <span class="version-tag ok">7.00 – 7.61 ✅</span>
        <span class="version-tag ok">8.00 – 9.00 ✅</span>
        <span class="version-tag ok">9.50 – 10.50 ✅</span>
        <span class="version-tag ok">11.00 – 12.00 ✅</span>
        <span class="version-tag ok">12.50 – 12.70 ✅</span>
        <span class="version-tag ok">13.00 – 13.50 ✅</span>
        <span class="version-tag ok">13.60 ✅ آخرین نسخه سازگار</span>
        <span class="version-tag no">14.00 و بالاتر ❌ پشتیبانی نمی‌شود</span>
      </div>
      <div class="alert note" style="margin-top:14px">
        💡 اگر کنسول شما روی نسخه ۱۴.۰۰ یا جدیدتر است، تا زمان انتشار اکسپلویت جدید، <strong>هیچ‌گونه به‌روزرسانی انجام ندهید</strong> و منتظر بمانید.
      </div>
    </div>

    <div class="card">
      <h2>🔧 گام اول: غیرفعال‌سازی به‌روزرسانی خودکار</h2>
      <div class="step-row">
        <span class="step-num">۱</span>
        <div><strong>تنظیمات → سیستم → به‌روزرسانی سیستم</strong> → هر دو گزینه «دانلود خودکار» و «نصب خودکار» را غیرفعال کنید</div>
      </div>
      <div class="step-row">
        <span class="step-num">۲</span>
        <div><strong>تنظیمات → شبکه → اتصال اینترنت</strong> → برای اطمینان، اتصال اینترنت را تا پایان کار قطع کنید</div>
      </div>
    </div>

    <div class="card">
      <h2>🌐 گام دوم: تنظیم DNS (مسدودسازی سرورهای سونی)</h2>
      <p style="margin-bottom:12px">این DNS سرورهای رسمی به‌روزرسانی سونی را مسدود می‌کند و مانع ارسال اطلاعات کنسول می‌شود:</p>
      <div class="link-box">
DNS اصلی:  45.56.67.85
DNS فرعی:  — خالی بگذارید یا 62.210.38.117
      </div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('DNS اصلی: 45.56.67.85\nDNS فرعی: 62.210.38.117').then(()=>alert('✅ کپی شد!'))">📋 کپی آدرس‌ها</button>
      <div class="step" style="margin-top:16px">
        <div class="step-row">
          <span class="step-num">۱</span>
          <div><strong>تنظیمات → شبکه → تنظیمات اتصال اینترنت → سفارشی</strong></div>
        </div>
        <div class="step-row">
          <span class="step-num">۲</span>
          <div>تنظیمات IP: خودکار | نام میزبان DHCP: مشخص نکنید | پروکسی: استفاده نکنید</div>
        </div>
        <div class="step-row">
          <span class="step-num">۳</span>
          <div>DNS: <strong>دستی</strong> → مقادیر بالا را وارد کنید</div>
        </div>
      </div>
      <div class="alert success" style="margin-top:14px">
        ✅ این آدرس‌های عددی در تمام اپراتورهای ایران بدون فیلترشکن کار می‌کنند و هیچ‌گاه مسدود نمی‌شوند.
      </div>
    </div>

    <div class="card">
      <h2>🚀 گام سوم: اجرای جیلبریک Relapse</h2>
      <p style="margin-bottom:14px">از بخش <strong>دفترچه راهنما / راهنمای کاربر</strong> در تنظیمات PS5، یکی از آدرس‌های زیر را در نوار آدرس وارد کنید:</p>

      <h3>میزبان اصلی پیشنهادی:</h3>
      <div class="link-box">https://ps5.thegate.network</div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('https://ps5.thegate.network').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
      <div class="alert success">✅ بدون فیلترشکن — سرور مستقل</div>

      <h3>میزبان جایگزین شماره ۱:</h3>
      <div class="link-box">https://relapse.jb-host.ir</div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('https://relapse.jb-host.ir').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
      <div class="alert success">✅ دامنه داخلی .ir — تضمین دسترسی</div>

      <h3>میزبان رسمی توسعه‌دهنده:</h3>
      <div class="link-box">https://ntfargo.github.io/Relapse-Exploit</div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('https://ntfargo.github.io/Relapse-Exploit').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
      <div class="alert note">⚠️ این لینک روی گیت‌هاب قرار دارد — در برخی اپراتورها ممکن است نیاز به یک‌بار باز شدن با فیلترشکن داشته باشد</div>

      <h3 style="margin-top:22px">مراحل اجرا:</h3>
      <ul>
        <li>🔹 صفحه بارگذاری می‌شود — ممکن است ۱ تا ۳ بار تلاش نیاز باشد</li>
        <li>🔹 پس از موفقیت، منتظر بمانید تا مرحله هسته کامل شود (چند ثانیه)</li>
        <li>🔹 دکمه <strong>R2</strong> روی دسته را فشار دهید → بارگذاری خودکار: kstuff → shadowmount → etaHEN</li>
        <li>🔹 نماد <strong>etaHEN</strong> در قسمت بازی‌ها ظاهر شد = جیلبریک فعال ✅</li>
        <li>🔹 جیلبریک موقت است — پس از خاموش و روشن کردن کامل کنسول، مجدداً تکرار کنید</li>
      </ul>
    </div>

    <div class="card">
      <h2>📦 ابزارهای تکمیلی</h2>
      <ul>
        <li><strong>nanoDNS 0.4:</strong> پس از جیلبریک اجرا کنید — اینترنت را فعال نگه می‌دارد ولی سرورهای آپدیت سونی را مسدود می‌کند</li>
        <li><strong>etaHEN:</strong> محیط اجرای برنامه‌های غیررسمی — امکان نصب فایل‌های PKG بازی و ابزارها</li>
        <li><strong>PS5Xplorer:</strong> مدیریت فایل و مرور حافظه داخلی کنسول</li>
        <li><strong>ShadowMountPlus:</strong> دسترسی به بخش‌های قفل‌شده سیستم برای نصب پلاگین‌ها</li>
      </ul>
    </div>
  </div>

  <!-- ================================== PS4 ================================== -->
  <div id="ps4" class="tab-content">
    <div class="card">
      <h2>✅ وضعیت سازگاری فریمور</h2>
      <div class="version-grid">
        <span class="version-tag ok">1.76 – 4.55 ✅</span>
        <span class="version-tag ok">5.05 / 5.07 ✅</span>
        <span class="version-tag ok">6.72 / 7.02 ✅</span>
        <span class="version-tag ok">7.50 / 7.55 ✅</span>
        <span class="version-tag ok">9.00 ✅</span>
        <span class="version-tag ok">9.03 – 11.02 ✅</span>
        <span class="version-tag ok">11.50 – 12.00 ✅</span>
        <span class="version-tag ok">12.50 – 13.00 ✅</span>
        <span class="version-tag ok">13.50 / 13.52 ✅ آخرین نسخه</span>
      </div>
    </div>

    <div class="card">
      <h2>🌐 تنظیم DNS</h2>
      <div class="link-box">
DNS اصلی:  165.227.83.145
DNS فرعی:  192.241.221.79
      </div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('DNS اصلی: 165.227.83.145\nDNS فرعی: 192.241.221.79').then(()=>alert('✅ کپی شد!'))">📋 کپی آدرس‌ها</button>
      <p style="margin-top:12px">مسیر: تنظیمات → شبکه → تنظیمات اتصال اینترنت → سفارشی → DNS دستی</p>
      <div class="alert success">✅ بدون فیلترشکن — در تمام اپراتورها کار می‌کند</div>
    </div>

    <div class="card">
      <h2>🚀 میزبان‌های جیلبریک بر اساس نسخه</h2>

      <h3>نسخه ۵.۰۵ تا ۹.۰۰:</h3>
      <div class="link-box">https://cthugha.thegate.network</div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('https://cthugha.thegate.network').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
      <div class="alert success">✅ میزبان رسمی Al-Azif — بدون فیلترشکن</div>

      <h3>نسخه ۹.۰۳ تا ۱۱.۰۲:</h3>
      <div class="link-box">https://ithaqua.thegate.network</div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('https://ithaqua.thegate.network').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
      <div class="alert success">✅ اکسپلویت Ithaqua — بدون فیلترشکن</div>

      <h3>نسخه ۱۱.۵۰ تا ۱۳.۰۰:</h3>
      <div class="link-box">https://psfree.jb-host.ir</div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('https://psfree.jb-host.ir').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
      <div class="alert success">✅ دامنه داخلی .ir — همیشه در دسترس</div>

      <h3>نسخه ۱۳.۵۰ تا ۱۳.۵۲:</h3>
      <div class="alert info">
        از روش <strong>PPPwn</strong> از طریق کابل شبکه + فایل روی فلش مموری استفاده کنید. پس از فعال‌سازی، GoldHEN را نصب نمایید.
      </div>
      <div class="link-box">https://ps4host.p30day.ir</div>
      <button class="btn-copy" onclick="navigator.clipboard.writeText('https://ps4host.p30day.ir').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
      <div class="alert success">✅ میزبان داخلی — بدون فیلترشکن</div>
    </div>

    <div class="card">
      <h2>📦 GoldHEN — قلب جیلبریک PS4</h2>
      <ul>
        <li><strong>آخرین نسخه:</strong> GoldHEN v2.4</li>
        <li><strong>سرور فایل:</strong> نصب بازی‌ها از طریق فلش مموری یا شبکه</li>
        <li><strong>FTP:</strong> دسترسی کامل به فایل‌های کنسول از طریق کامپیوتر</li>
        <li><strong>پلاگین‌ها:</strong> تقلب در بازی‌ها، تغییرات گرافیکی، غیرفعال‌سازی محدودیت‌ها</li>
        <li><strong>مدیریت بسته‌ها:</strong> نصب مستقیم فایل‌های PKG</li>
      </ul>
    </div>
  </div>

  <!-- ================================== FAQ ================================== -->
  <div id="faq" class="tab-content">
    <div class="card">
      <h2>📋 لیست کامل میزبان‌های فعال</h2>
      <table class="host-table">
        <thead>
          <tr>
            <th>کنسول</th>
            <th>محدوده نسخه</th>
            <th>لینک میزبان</th>
            <th>بدون فیلترشکن</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>PS5</td>
            <td>7.00 – 13.60</td>
            <td>ps5.thegate.network</td>
            <td class="check-yes">✅</td>
          </tr>
          <tr>
            <td>PS5</td>
            <td>7.00 – 13.60</td>
            <td>relapse.jb-host.ir</td>
            <td class="check-yes">✅</td>
          </tr>
          <tr>
            <td>PS4</td>
            <td>5.05 – 9.00</td>
            <td>cthugha.thegate.network</td>
            <td class="check-yes">✅</td>
          </tr>
          <tr>
            <td>PS4</td>
            <td>9.03 – 11.02</td>
            <td>ithaqua.thegate.network</td>
            <td class="check-yes">✅</td>
          </tr>
          <tr>
            <td>PS4</td>
            <td>11.50 – 13.00</td>
            <td>psfree.jb-host.ir</td>
            <td class="check-yes">✅</td>
          </tr>
          <tr>
            <td>PS4</td>
            <td>13.50 – 13.52</td>
            <td>ps4host.p30day.ir</td>
            <td class="check-yes">✅</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="card">
      <h2>❓ سؤالات متداول</h2>

      <h3>جیلبریک دائمی است؟</h3>
      <p>خیر — در حال حاضر جیلبریک هر دو کنسول <strong>موقت</strong> است. پس از خاموش و روشن کردن کامل کنسول، باید مجدداً میزبان را باز کرده و مراحل را تکرار کنید.</p>
      <div class="spacer"></div>

      <h3>آیا حساب کاربری مسدود می‌شود؟</h3>
      <p>اگر پس از جیلبریک وارد حساب کاربری شوید یا بازی آنلاین انجام دهید، <strong>احتمال مسدودی بسیار بالا</strong> است. توصیه می‌شود هیچ‌گاه وارد حساب نشوید و برای بازی آنلاین از کنسول دیگری استفاده کنید.</p>
      <div class="spacer"></div>

      <h3>چرا صفحه میزبان باز نمی‌شود؟</h3>
      <p>کش مرورگر را خالی کنید → کنسول را ریبوت کنید → DNS را مجدداً بررسی کنید → یک بار اینترنت را قطع و وصل کنید. لینک‌های با دامنه <code>.ir</code> همیشه اولویت دارند.</p>
      <div class="spacer"></div>

      <h3>بازی‌های کپی را چگونه نصب کنم؟</h3>
      <p>پس از فعال‌سازی جیلبریک، فایل‌های PKG بازی را روی فلش مموری با فرمت exFAT کپی کرده و به کنسول متصل کنید → از بخش مدیریت بسته‌ها نصب کنید. برای PS5 نیاز به فایل‌های سازگار با نسخه جاری سیستم است.</p>
      <div class="spacer"></div>

      <h3>آیا می‌توانم به اینترنت متصل بمانم؟</h3>
      <p>در PS5 با اجرای nanoDNS می‌توانید اینترنت را نگه دارید ولی سرورهای سونی مسدود می‌مانند. در PS4 پس از جیلبریک، اتصال اینترنت را فقط با DNS تغییر داده شده نگه دارید و وارد حساب کاربری نشوید.</p>
    </div>

    <div class="card">
      <h2>⚠️ لیست ممنوعات</h2>
      <ul style="color:#ffb3b3">
        <li>❌ به‌روزرسانی سیستم عامل کنسول — هرگز</li>
        <li>❌ ورود به حساب کاربری شبکه پلی‌استیشن</li>
        <li>❌ بازی آنلاین و رقابتی پس از جیلبریک</li>
        <li>❌ اشتراک‌گذاری شناسه دستگاه در شبکه‌های عمومی</li>
        <li>❌ بازگذاشتن پسورد روی کنسول بدون نظارت</li>
      </ul>
    </div>
  </div>

  <footer>
    <p><strong>VORTEXPLAY</strong> © ۱۴۰۴ — ۱۴۰۵ | تمام میزبان‌ها از منابع عمومی و معتبر جامعه هکینگ کنسول گرفته شده‌اند</p>
    <p style="margin-top:8px;color:#557799">این سایت صرفاً جنبه آموزشی دارد. استفاده و مسئولیت هرگونه کاربرد با کاربر است.</p>
  </footer>
</div>

<script>
function switchTab(id){
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  document.querySelectorAll('.tab-content').forEach(c=>c.classList.remove('active'));
  event.target.classList.add('active');
  document.getElementById(id).classList.add('active');
}
</script>
</body>
</html>
