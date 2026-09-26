<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY 👑 | سامانه سلطنتی</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700;900&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{
  --gold:#D4AF37;
  --gold-light:#F4E4BC;
  --gold-dark:#996515;
  --royal-purple:#2A1040;
  --deep-dark:#0F051A;
  --accent:#FFD700;
  --text-light:#F9F2E8;
  --shadow-gold:0 0 20px rgba(212,175,55,0.4);
  --shadow-strong:0 0 40px rgba(255,215,0,0.6);
}
body{
  font-family:'Tajawal',sans-serif;
  min-height:100vh;
  background:linear-gradient(135deg,#0F051A 0%,#1A0A2E 50%,#2A1040 100%);
  color:var(--text-light);
  overflow-x:hidden;
}
.bg-pattern{
  position:fixed;inset:0;
  background-image:
    radial-gradient(circle at 20% 30%,rgba(212,175,55,0.08) 0%,transparent 50%),
    radial-gradient(circle at 80% 70%,rgba(255,215,0,0.06) 0%,transparent 50%);
  pointer-events:none;z-index:0;
}
.neon-ring{
  position:fixed;top:50%;left:50%;transform:translate(-50%,-50%);
  width:500px;height:500px;border-radius:50%;
  border:1px solid rgba(212,175,55,0.15);
  box-shadow:inset 0 0 60px rgba(212,175,55,0.1),0 0 40px rgba(212,175,55,0.15);
  pointer-events:none;z-index:0;
}
.page-container{position:relative;z-index:1}
header{
  text-align:center;padding:30px 20px;
  border-bottom:1px solid rgba(212,175,55,0.2);
  background:linear-gradient(180deg,rgba(212,175,55,0.1) 0%,transparent 100%);
}
.logo-title{
  font-family:'Cinzel',serif;font-size:clamp(2rem,5vw,3.5rem);font-weight:900;
  background:linear-gradient(90deg,var(--gold-dark),var(--accent),var(--gold-dark));
  -webkit-background-clip:text;background-clip:text;color:transparent;
  text-shadow:0 0 30px rgba(255,215,0,0.3);
  letter-spacing:2px;
}
.subtitle{color:var(--gold-light);opacity:0.8;margin-top:8px;font-size:1rem}
.admin-toggle{
  position:absolute;top:20px;left:20px;
  background:transparent;border:1px solid var(--gold);color:var(--gold);
  padding:8px 16px;border-radius:8px;cursor:pointer;transition:0.3s;
  font-family:'Tajawal',sans-serif;
}
.admin-toggle:hover{background:rgba(212,175,55,0.15);box-shadow:var(--shadow-gold)}
.container{max-width:1200px;margin:0 auto;padding:30px 20px}
.section-title{
  font-family:'Cinzel',serif;font-size:1.8rem;margin:40px 0 20px;
  color:var(--accent);border-bottom:1px solid rgba(212,175,55,0.25);padding-bottom:10px;
}
.categories-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:25px}
.category-card{
  background:rgba(255,255,255,0.03);border:1px solid rgba(212,175,55,0.2);
  border-radius:16px;padding:25px;transition:0.4s;cursor:pointer;
  backdrop-filter:blur(8px);
}
.category-card:hover{
  transform:translateY(-5px);border-color:var(--accent);
  box-shadow:var(--shadow-gold);background:rgba(212,175,55,0.08);
}
.cat-icon{font-size:2.5rem;margin-bottom:12px}
.cat-name{font-family:'Cinzel',serif;font-size:1.3rem;color:var(--accent);margin-bottom:8px}
.cat-desc{color:var(--gold-light);opacity:0.75;font-size:0.9rem;line-height:1.6}
.cat-count{margin-top:12px;font-size:0.85rem;color:var(--gold);opacity:0.9}
.back-btn{
  display:inline-flex;align-items:center;gap:8px;
  color:var(--gold);text-decoration:none;margin-bottom:20px;cursor:pointer;
  transition:0.2s;
}
.back-btn:hover{color:var(--accent)}
.item-card{
  background:rgba(255,255,255,0.03);border:1px solid rgba(212,175,55,0.15);
  border-radius:12px;padding:20px;margin-bottom:15px;transition:0.3s;
}
.item-card:hover{border-color:rgba(212,175,55,0.4);background:rgba(212,175,55,0.05)}
.item-title{font-weight:700;color:var(--gold-light);margin-bottom:8px;font-size:1.1rem}
.item-desc{color:#ddd;opacity:0.85;font-size:0.9rem;line-height:1.7;margin-bottom:10px}
.item-link{
  display:inline-block;background:linear-gradient(90deg,var(--gold-dark),var(--gold));
  color:#000;padding:8px 20px;border-radius:8px;text-decoration:none;font-weight:700;
  transition:0.3s;margin-top:5px;
}
.item-link:hover{box-shadow:var(--shadow-strong);transform:scale(1.03)}
.item-img{max-width:100%;border-radius:8px;margin:10px 0;max-height:200px;object-fit:cover}

/* === پنل مدیریت === */
.admin-panel{
  position:fixed;inset:0;background:rgba(0,0,0,0.92);z-index:999;
  display:none;align-items:center;justify-content:center;padding:20px;
}
.admin-panel.active{display:flex}
.admin-box{
  background:linear-gradient(135deg,#1A0A2E,#2A1040);
  border:2px solid var(--gold);border-radius:20px;padding:30px;
  max-width:500px;width:100%;max-height:90vh;overflow-y:auto;
  box-shadow:var(--shadow-strong);
}
.admin-box h2{text-align:center;color:var(--accent);margin-bottom:25px;font-family:'Cinzel',serif}
.input-field{
  width:100%;padding:12px 15px;margin:8px 0;border-radius:8px;
  border:1px solid rgba(212,175,55,0.3);background:rgba(0,0,0,0.3);
  color:#fff;font-size:1rem;font-family:inherit;
}
.input-field:focus{outline:none;border-color:var(--accent);box-shadow:0 0 10px rgba(255,215,0,0.3)}
.btn{
  padding:12px 20px;border-radius:8px;border:none;font-weight:700;cursor:pointer;
  font-family:inherit;transition:0.3s;margin:5px;
}
.btn-gold{background:linear-gradient(90deg,var(--gold-dark),var(--gold));color:#000;width:100%;margin-top:10px}
.btn-gold:hover{box-shadow:var(--shadow-strong)}
.btn-secondary{background:transparent;border:1px solid var(--gold);color:var(--gold)}
.btn-danger{background:transparent;border:1px solid #ff6b6b;color:#ff6b6b}
.btn-danger:hover{background:rgba(255,107,107,0.1)}
.tabs{display:flex;gap:10px;margin-bottom:20px;flex-wrap:wrap}
.tab{
  padding:10px 15px;border-radius:8px;border:1px solid rgba(212,175,55,0.3);
  cursor:pointer;color:var(--gold-light);transition:0.2s;font-size:0.9rem;
}
.tab.active{background:rgba(212,175,55,0.2);border-color:var(--accent);color:var(--accent)}
.tab-content{display:none}
.tab-content.active{display:block}
.hidden-section{display:none}
.empty-state{text-align:center;padding:40px;color:var(--gold-light);opacity:0.5}
.code-output{
  background:#000;border:1px solid #444;border-radius:8px;padding:15px;
  font-family:monospace;font-size:0.85rem;white-space:pre-wrap;word-break:break-all;
  color:#90EE90;margin-top:15px;max-height:250px;overflow:auto;
}
.copy-note{color:#87CEEB;font-size:0.85rem;margin-top:8px}
footer{
  text-align:center;padding:30px 20px;margin-top:60px;
  border-top:1px solid rgba(212,175,55,0.15);color:var(--gold-light);opacity:0.6;
  font-size:0.85rem;
}
</style>
</head>
<body>
<div class="bg-pattern"></div>
<div class="neon-ring"></div>

<div class="page-container">
<header>
  <button class="admin-toggle" onclick="openAdminPanel()">⚙️ مدیریت</button>
  <h1 class="logo-title">VORTEXPLAY</h1>
  <p class="subtitle">سامانه سلطنتی محتوا و فایل‌ها</p>
</header>

<div class="container">
  <!-- صفحه اصلی -->
  <div id="home-page">
    <h2 class="section-title">دسته‌بندی‌ها</h2>
    <div id="categories-container" class="categories-grid">
      <!-- دسته‌بندی‌ها از اینجا اضافه می‌شوند -->
    </div>
  </div>

  <!-- صفحه داخل دسته -->
  <div id="category-page" class="hidden-section">
    <span class="back-btn" onclick="goBack()">← بازگشت به صفحه اصلی</span>
    <h2 id="current-cat-name" class="section-title"></h2>
    <p id="current-cat-desc" style="color:var(--gold-light);opacity:0.7;margin-bottom:20px"></p>
    <div id="items-container"></div>
  </div>
</div>

<footer>
  VORTEXPLAY © 2026 | سامانه سلطنتی | هاست دائمی از طریق گیت‌هاب و کلادفلر
</footer>
</div>

<!-- پنل مدیریت -->
<div id="admin-panel" class="admin-panel">
  <div class="admin-box">
    <h2>🔐 پنل مدیریت</h2>
    
    <!-- ورود -->
    <div id="login-form">
      <input type="password" id="admin-pass" class="input-field" placeholder="رمز ۳۲ رقمی را وارد کنید">
      <button class="btn btn-gold" onclick="checkPass()">ورود به پنل</button>
    </div>

    <!-- محتوای پنل پس از ورود -->
    <div id="admin-content" style="display:none">
      <div class="tabs">
        <div class="tab active" data-tab="cats">📂 دسته‌بندی‌ها</div>
        <div class="tab" data-tab="items">📄 افزودن پیام/فایل</div>
        <div class="tab" data-tab="code">💻 کد تولید</div>
        <div class="tab" data-tab="visual">🎨 ظاهر سایت</div>
      </div>

      <!-- تب دسته‌بندی‌ها -->
      <div class="tab-content active" id="tab-cats">
        <h3 style="color:var(--accent);margin-bottom:15px">ایجاد دسته‌بندی جدید</h3>
        <input type="text" id="cat-name" class="input-field" placeholder="نام دسته‌بندی">
        <input type="text" id="cat-desc" class="input-field" placeholder="توضیح کوتاه دسته‌بندی">
        <input type="text" id="cat-icon" class="input-field" placeholder="آیکون (مثلاً 🎮 یا عکس لینک)">
        <button class="btn btn-gold" onclick="addCategory()">✅ ایجاد دسته‌بندی</button>
        <div id="cat-list" style="margin-top:25px"></div>
      </div>

      <!-- تب افزودن پیام/فایل -->
      <div class="tab-content" id="tab-items">
        <h3 style="color:var(--accent);margin-bottom:15px">افزودن پیام یا فایل به دسته‌بندی</h3>
        <select id="target-cat" class="input-field">
          <option value="">انتخاب دسته‌بندی مقصد...</option>
        </select>
        <input type="text" id="item-title" class="input-field" placeholder="عنوان پیام/فایل">
        <textarea id="item-desc" class="input-field" rows="4" placeholder="توضیحات و متن کامل"></textarea>
        <input type="text" id="item-img" class="input-field" placeholder="لینک عکس/کاور (اختیاری)">
        <input type="text" id="item-link" class="input-field" placeholder="لینک دانلود یا فایل (اختیاری)">
        <button class="btn btn-gold" onclick="addItem()">✅ افزودن محتوا</button>
        <div id="item-list" style="margin-top:25px"></div>
      </div>

      <!-- تب کد تولید -->
      <div class="tab-content" id="tab-code">
        <h3 style="color:var(--accent);margin-bottom:15px">کد نهایی برای قرار دادن در سایت</h3>
        <p style="color:#aaa;font-size:0.9rem;margin-bottom:10px">این کد را کپی کن و جای کل کد فایل index.html قرار بده، سپس در گیت‌هاب ذخیره کن:</p>
        <div class="code-output" id="full-code-box">کد در حال بارگذاری...</div>
        <p class="copy-note">💡 پس از تغییر، فایل را در گیت‌هاب ذخیره کن → کلادفلر خودکار به‌روزرسانی می‌شود</p>
        <button class="btn btn-secondary" onclick="copyCode()" style="margin-top:10px">📋 کپی کد کامل</button>
      </div>

      <!-- تب ظاهر -->
      <div class="tab-content" id="tab-visual">
        <h3 style="color:var(--accent);margin-bottom:15px">تنظیمات ظاهری</h3>
        <input type="text" id="site-title" class="input-field" placeholder="نام سایت" value="VORTEXPLAY">
        <input type="text" id="site-subtitle" class="input-field" placeholder="زیرنویس سایت" value="سامانه سلطنتی محتوا و فایل‌ها">
        <button class="btn btn-gold" onclick="saveVisual()">ذخیره ظاهر</button>
      </div>

      <button class="btn btn-secondary" style="margin-top:25px;width:100%" onclick="closeAdminPanel()">بستن پنل</button>
    </div>
  </div>
</div>

<script>
// === داده‌های اصلی ===
const ADMIN_PASS = "K9#mP2$xR7!vL3@nQ5&bT1*wZ8%yA4^";
let categories = [];
let currentCatIndex = null;
let siteConfig = {
  title: "VORTEXPLAY",
  subtitle: "سامانه سلطنتی محتوا و فایل‌ها"
};

// === بارگذاری اولیه ===
document.addEventListener('DOMContentLoaded', () => {
  loadData();
  renderCategories();
  setupTabs();
});

function loadData(){
  const saved = localStorage.getItem('vortex_data');
  if(saved) categories = JSON.parse(saved);
  const cfg = localStorage.getItem('vortex_config');
  if(cfg){
    siteConfig = JSON.parse(cfg);
    document.querySelector('.logo-title').textContent = siteConfig.title;
    document.querySelector('.subtitle').textContent = siteConfig.subtitle;
    document.getElementById('site-title').value = siteConfig.title;
    document.getElementById('site-subtitle').value = siteConfig.subtitle;
  }
}
function saveData(){
  localStorage.setItem('vortex_data', JSON.stringify(categories));
  updateCodeOutput();
}

// === پنل مدیریت ===
function openAdminPanel(){
  document.getElementById('admin-panel').classList.add('active');
  document.getElementById('login-form').style.display = 'block';
  document.getElementById('admin-content').style.display = 'none';
  document.getElementById('admin-pass').value = '';
}
function closeAdminPanel(){
  document.getElementById('admin-panel').classList.remove('active');
  currentCatIndex = null;
}
function checkPass(){
  const pass = document.getElementById('admin-pass').value;
  if(pass === ADMIN_PASS){
    document.getElementById('login-form').style.display = 'none';
    document.getElementById('admin-content').style.display = 'block';
    updateCategorySelect();
    renderCatList();
    updateCodeOutput();
  }else{
    alert('❌ رمز اشتباه است!');
  }
}

// === تب‌ها ===
function setupTabs(){
  document.querySelectorAll('.tab').forEach(tab=>{
    tab.onclick = ()=>{
      document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
      document.querySelectorAll('.tab-content').forEach(c=>c.classList.remove('active'));
      tab.classList.add('active');
      document.getElementById('tab-'+tab.dataset.tab).classList.add('active');
      if(tab.dataset.tab === 'code') updateCodeOutput();
    };
  });
}

// === دسته‌بندی‌ها ===
function addCategory(){
  const name = document.getElementById('cat-name').value.trim();
  const desc = document.getElementById('cat-desc').value.trim();
  const icon = document.getElementById('cat-icon').value.trim() || '📁';
  if(!name){alert('نام دسته‌بندی را بنویسید');return}
  categories.push({name,desc,icon,items:[]});
  saveData();renderCategories();updateCategorySelect();renderCatList();
  document.getElementById('cat-name').value='';document.getElementById('cat-desc').value='';document.getElementById('cat-icon').value='';
}
function renderCategories(){
  const container = document.getElementById('categories-container');
  if(!categories.length){
    container.innerHTML = '<p class="empty-state">هنوز دسته‌بندی تعریف نشده ⚙️ از پنل مدیریت ایجاد کنید</p>';
    return;
  }
  container.innerHTML = categories.map((cat,idx)=>`
    <div class="category-card" onclick="openCategory(${idx})">
      <div class="cat-icon">${cat.icon}</div>
      <h3 class="cat-name">${cat.name}</h3>
      <p class="cat-desc">${cat.desc || 'بدون توضیح'}</p>
      <p class="cat-count">${cat.items.length} مورد</p>
    </div>
  `).join('');
}
function openCategory(idx){
  currentCatIndex = idx;
  document.getElementById('home-page').classList.add('hidden-section');
  document.getElementById('category-page').classList.remove('hidden-section');
  const cat = categories[idx];
  document.getElementById('current-cat-name').textContent = cat.icon+' '+cat.name;
  document.getElementById('current-cat-desc').textContent = cat.desc;
  renderItems(cat.items);
}
function goBack(){
  currentCatIndex = null;
  document.getElementById('home-page').classList.remove('hidden-section');
  document.getElementById('category-page').classList.add('hidden-section');
}
function renderItems(items){
  const container = document.getElementById('items-container');
  if(!items.length){
    container.innerHTML = '<p class="empty-state">هنوز محتوایی اضافه نشده</p>';
    return;
  }
  container.innerHTML = items.map((item,i)=>`
    <div class="item-card">
      <h4 class="item-title">${item.title}</h4>
      ${item.img?`<img src="${item.img}" class="item-img" alt="">`:''}
      <p class="item-desc">${item.desc.replace(/\n/g,'<br>')}</p>
      ${item.link?`<a href="${item.link}" target="_blank" class="item-link">🔗 دریافت / دانلود</a>`:''}
    </div>
  `).join('');
}
function updateCategorySelect(){
  const select = document.getElementById('target-cat');
  select.innerHTML = '<option value="">انتخاب دسته‌بندی مقصد...</option>' +
    categories.map((cat,i)=>`<option value="${i}">${cat.icon} ${cat.name}</option>`).join('');
}
function renderCatList(){
  const list = document.getElementById('cat-list');
  if(!categories.length){list.innerHTML='<p style="opacity:0.6">هنوز دسته‌بندی وجود ندارد</p>';return}
  list.innerHTML = categories.map((cat,i)=>`
    <div style="padding:10px;border-bottom:1px solid rgba(212,175,55,0.15);display:flex;justify-content:space-between;align-items:center">
      <span>${cat.icon} ${cat.name} (${cat.items.length})</span>
      <button class="btn btn-danger" style="padding:5px 10px;font-size:0.8rem" onclick="delCat(${i})">حذف</button>
    </div>
  `).join('');
}
function delCat(idx){
  if(confirm('آیا مطمئن هستید؟ تمام محتوای این دسته هم حذف می‌شود')){
    categories.splice(idx,1);
    saveData();renderCategories();updateCategorySelect();renderCatList();
    if(currentCatIndex===idx) goBack();
  }
}

// === افزودن آیتم ===
function addItem(){
  const catIdx = parseInt(document.getElementById('target-cat').value);
  const title = document.getElementById('item-title').value.trim();
  const desc = document.getElementById('item-desc').value.trim();
  const img = document.getElementById('item-img').value.trim();
  const link = document.getElementById('item-link').value.trim();
  if(isNaN(catIdx) || !title){alert('دسته‌بندی و عنوان را تکمیل کنید');return}
  categories[catIdx].items.push({title,desc,img,link});
  saveData();renderCatList();
  if(currentCatIndex===catIdx) renderItems(categories[catIdx].items);
  alert('✅ محتوا اضافه شد! حالا به تب «کد تولید» برو و کد جدید را کپی کن');
  document.getElementById('item-title').value='';document.getElementById('item-desc').value='';
  document.getElementById('item-img').value='';document.getElementById('item-link').value='';
}

// === ظاهر ===
function saveVisual(){
  siteConfig.title = document.getElementById('site-title').value.trim() || 'VORTEXPLAY';
  siteConfig.subtitle = document.getElementById('site-subtitle').value.trim() || 'سامانه سلطنتی محتوا و فایل‌ها';
  localStorage.setItem('vortex_config', JSON.stringify(siteConfig));
  document.querySelector('.logo-title').textContent = siteConfig.title;
  document.querySelector('.subtitle').textContent = siteConfig.subtitle;
  alert('✅ ظاهر ذخیره شد! کد جدید را در تب کد تولید بگیر');
  updateCodeOutput();
}

// === تولید کد کامل برای گیت‌هاب ===
function updateCodeOutput(){
  const dataStr = JSON.stringify({categories,siteConfig});
  const codeBox = document.getElementById('full-code-box');
  codeBox.textContent = generateFullPageCode(dataStr);
}
function generateFullPageCode(dataStr){
  // کد کامل صفحه با داده‌های فعلی
  return `<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>${siteConfig.title} 👑</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700;900&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{--gold:#D4AF37;--gold-light:#F4E4BC;--gold-dark:#996515;--royal-purple:#2A1040;--deep-dark:#0F051A;--accent:#FFD700;--text-light:#F9F2E8;--shadow-gold:0 0 20px rgba(212,175,55,0.4);--shadow-strong:0 0 40px rgba(255,215,0,0.6)}
body{font-family:'Tajawal',sans-serif;min-height:100vh;background:linear-gradient(135deg,#0F051A 0%,#1A0A2E 50%,#2A1040 100%);color:var(--text-light);overflow-x:hidden}
.bg-pattern{position:fixed;inset:0;background-image:radial-gradient(circle at 20% 30%,rgba(212,175,55,0.08) 0%,transparent 50%),radial-gradient(circle at 80% 70%,rgba(255,215,0,0.06) 0%,transparent 50%);pointer-events:none;z-index:0}
.neon-ring{position:fixed;top:50%;left:50%;transform:translate(-50%,-50%);width:500px;height:500px;border-radius:50%;border:1px solid rgba(212,175,55,0.15);box-shadow:inset 0 0 60px rgba(212,175,55,0.1),0 0 40px rgba(212,175,55,0.15);pointer-events:none;z-index:0}
.page-container{position:relative;z-index:1}
header{text-align:center;padding:30px 20px;border-bottom:1px solid rgba(212,175,55,0.2);background:linear-gradient(180deg,rgba(212,175,55,0.1) 0%,transparent 100%)}
.logo-title{font-family:'Cinzel',serif;font-size:clamp(2rem,5vw,3.5rem);font-weight:900;background:linear-gradient(90deg,var(--gold-dark),var(--accent),var(--gold-dark));-webkit-background-clip:text;background-clip:text;color:transparent;letter-spacing:2px}
.subtitle{color:var(--gold-light);opacity:0.8;margin-top:8px;font-size:1rem}
.admin-toggle{position:absolute;top:20px;left:20px;background:transparent;border:1px solid var(--gold);color:var(--gold);padding:8px 16px;border-radius:8px;cursor:pointer;transition:0.3s;font-family:'Tajawal',sans-serif}
.admin-toggle:hover{background:rgba(212,175,55,0.15);box-shadow:var(--shadow-gold)}
.container{max-width:1200px;margin:0 auto;padding:30px 20px}
.section-title{font-family:'Cinzel',serif;font-size:1.8rem;margin:40px 0 20px;color:var(--accent);border-bottom:1px solid rgba(212,175,55,0.25);padding-bottom:10px}
.categories-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:25px}
.category-card{background:rgba(255,255,255,0.03);border:1px solid rgba(212,175,55,0.2);border-radius:16px;padding:25px;transition:0.4s;cursor:pointer;backdrop-filter:blur(8px)}
.category-card:hover{transform:translateY(-5px);border-color:var(--accent);box-shadow:var(--shadow-gold);background:rgba(212,175,55,0.08)}
.cat-icon{font-size:2.5rem;margin-bottom:12px}
.cat-name{font-family:'Cinzel',serif;font-size:1.3rem;color:var(--accent);margin-bottom:8px}
.cat-desc{color:var(--gold-light);opacity:0.75;font-size:0.9rem;line-height:1.6}
.cat-count{margin-top:12px;font-size:0.85rem;color:var(--gold);opacity:0.9}
.back-btn{display:inline-flex;align-items:center;gap:8px;color:var(--gold);text-decoration:none;margin-bottom:20px;cursor:pointer;transition:0.2s}
.back-btn:hover{color:var(--accent)}
.item-card{background:rgba(255,255,255,0.03);border:1px solid rgba(212,175,55,0.15);border-radius:12px;padding:20px;margin-bottom:15px;transition:0.3s}
.item-card:hover{border-color:rgba(212,175,55,0.4);background:rgba(212,175,55,0.05)}
.item-title{font-weight:700;color:var(--gold-light);margin-bottom:8px;font-size:1.1rem}
.item-desc{color:#ddd;opacity:0.85;font-size:0.9rem;line-height:1.7;margin-bottom:10px}
.item-link{display:inline-block;background:linear-gradient(90deg,var(--gold-dark),var(--gold));color:#000;padding:8px 20px;border-radius:8px;text-decoration:none;font-weight:700;transition:0.3s;margin-top:5px}
.item-link:hover{box-shadow:var(--shadow-strong);transform:scale(1.03)}
.item-img{max-width:100%;border-radius:8px;margin:10px 0;max-height:200px;object-fit:cover}
.hidden-section{display:none}
.empty-state{text-align:center;padding:40px;color:var(--gold-light);opacity:0.5}
footer{text-align:center;padding:30px 20px;margin-top:60px;border-top:1px solid rgba(212,175,55,0.15);color:var(--gold-light);opacity:0.6;font-size:0.85rem}
</style>
</head>
<body>
<div class="bg-pattern"></div>
<div class="neon-ring"></div>
<div class="page-container">
<header>
  <h1 class="logo-title">${siteConfig.title}</h1>
  <p class="subtitle">${siteConfig.subtitle}</p>
</header>
<div class="container">
  <div id="home-page">
    <h2 class="section-title">دسته‌بندی‌ها</h2>
    <div id="cats">${generateCategoriesHTML()}</div>
  </div>
</div>
<footer>VORTEXPLAY © 2026 | هاست دائمی گیت‌هاب + کلادفلر</footer>
</div>
<script>
const DATA = ${dataStr};
function renderHome(){
  const cont = document.getElementById('cats');
  if(!DATA.categories.length){
    cont.innerHTML = '<p class="empty-state">به زودی محتوا بارگذاری می‌شود ✨</p>';
    return;
  }
  cont.innerHTML = DATA.categories.map((cat,idx)=>\`
    <div class="category-card" onclick="openCat(\${idx})">
      <div class="cat-icon">\${cat.icon}</div>
      <h3 class="cat-name">\${cat.name}</h3>
      <p class="cat-desc">\${cat.desc || 'مشاهده محتوا'}</p>
      <p class="cat-count">\${cat.items.length} مورد</p>
    </div>
  \`).join('');
}
function openCat(idx){
  const cat = DATA.categories[idx];
  document.getElementById('home-page').innerHTML = \`
    <span class="back-btn" onclick="location.reload()">← بازگشت</span>
    <h2 class="section-title">\${cat.icon} \${cat.name}</h2>
    <p style="color:var(--gold-light);opacity:0.7;margin-bottom:20px">\${cat.desc}</p>
    \${cat.items.length===0?'<p class=\"empty-state\">هنوز محتوایی قرار نگرفته ✨</p>':cat.items.map(item=>\`
      <div class="item-card">
        <h4 class="item-title">\${item.title}</h4>
        \${item.img?\`<img src=\"\${item.img}\" class=\"item-img\" alt=\"\">\`:''}
        <p class="item-desc">\${item.desc.replace(/\\\\n/g,'<br>')}</p>
        \${item.link?\`<a href=\"\${item.link}\" target=\"_blank\" class=\"item-link\">🔗 دریافت</a>\`:''}
      </div>
    \`).join('')}
  \`;
}
renderHome();
</script>
</body>
</html>`;
}
function generateCategoriesHTML(){
  if(!categories.length) return '<p class="empty-state">هنوز دسته‌بندی تعریف نشده ⚙️</p>';
  return categories.map((cat,i)=>`
    <div class="category-card" onclick="openCategory(${i})">
      <div class="cat-icon">${cat.icon}</div>
      <h3 class="cat-name">${cat.name}</h3>
      <p class="cat-desc">${cat.desc || 'مشاهده محتوا'}</p>
      <p class="cat-count">${cat.items.length} مورد</p>
    </div>
  `).join('');
}
function copyCode(){
  const code = document.getElementById('full-code-box').textContent;
  navigator.clipboard.writeText(code).then(()=>{
    alert('✅ کد کامل کپی شد! در گیت‌هاب جایگزین کن و ذخیره کن');
  }).catch(()=>alert('کپی نشد — دستی انتخاب و کپی کن'));
}
</script>
</body>
</html>
