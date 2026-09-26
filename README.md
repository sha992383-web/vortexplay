<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY 🎮 | Cyberpunk Edition</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}

:root{
  --neon-cyan: #00f0ff;
  --neon-pink: #ff00e5;
  --neon-purple: #b000ff;
  --neon-green: #00ff88;
  --neon-orange: #ff6600;
  --neon-yellow: #ffee00;
  --neon-red: #ff0055;
  --bg-black: #000000;
  --bg-navy: #0a0e27;
  --bg-deep-purple: #1a0033;
  --bg-ink: #000814;
  --text-ice: #e0f7ff;
  --text-ice-blue: #b0e0ff;
  --text-silver: #c0c0c0;
  --text-gold: #ffd700;
  --glow-cyan: 0 0 10px #00f0ff, 0 0 20px #00f0ff, 0 0 40px #00f0ff;
  --glow-pink: 0 0 10px #ff00e5, 0 0 20px #ff00e5, 0 0 40px #ff00e5;
  --glow-purple: 0 0 10px #b000ff, 0 0 20px #b000ff, 0 0 40px #b000ff;
  --glow-green: 0 0 10px #00ff88, 0 0 20px #00ff88, 0 0 40px #00ff88;
}

body{
  font-family:'Tajawal',sans-serif;
  min-height:100vh;
  background:
    radial-gradient(ellipse at top, #1a0033 0%, transparent 50%),
    radial-gradient(ellipse at bottom, #0a0e27 0%, transparent 50%),
    linear-gradient(180deg, #000000 0%, #000814 100%);
  color:var(--text-ice);
  overflow-x:hidden;
}

/* ========== پس‌زمینه لایه‌بندی شده ========== */
.bg-layer-1, .bg-layer-2, .bg-layer-3{
  position:fixed;inset:0;pointer-events:none;z-index:0
}
.bg-layer-2{
  background:
    linear-gradient(90deg, rgba(0,240,255,0.03) 1px, transparent 1px),
    linear-gradient(rgba(0,240,255,0.03) 1px, transparent 1px);
  background-size:60px 60px;
  transform:perspective(500px) rotateX(60deg);
  transform-origin:center top;
  mask-image:linear-gradient(to top, rgba(0,0,0,0.8), transparent);
  -webkit-mask-image:linear-gradient(to top, rgba(0,0,0,0.8), transparent);
  opacity:0.4
}

/* ذرات نئونی */
.particle{
  position:fixed;width:4px;height:4px;border-radius:50%;
  pointer-events:none;z-index:1;animation:floatUp 15s infinite ease-in-out
}
.p-cyan{background:var(--neon-cyan);box-shadow:var(--glow-cyan);animation-duration:18s}
.p-pink{background:var(--neon-pink);box-shadow:var(--glow-pink);animation-duration:22s;animation-delay:2s}
.p-purple{background:var(--neon-purple);box-shadow:var(--glow-purple);animation-duration:20s;animation-delay:5s}
@keyframes floatUp{
  0%{transform:translateY(100vh) translateX(0);opacity:0}
  10%{opacity:1}
  90%{opacity:1}
  100%{transform:translateY(-100px) translateX(20px);opacity:0}
}

/* اسکن لاین */
.scanline{
  position:fixed;top:0;left:0;width:100%;height:2px;
  background:linear-gradient(90deg, transparent, var(--neon-cyan), transparent);
  box-shadow:var(--glow-cyan);animation:scan 8s linear infinite;
  pointer-events:none;z-index:999;opacity:0.3
}
@keyframes scan{0%{transform:translateY(0)}100%{transform:translateY(100vh)}}

.page-wrap{position:relative;z-index:1}

/* ========== هدر ========== */
header{
  position:relative;padding:30px 20px;text-align:center;
  border-bottom:1px solid rgba(0,240,255,0.2);
  background:linear-gradient(180deg, rgba(0,240,255,0.08) 0%, transparent 100%)
}
.admin-btn{
  position:absolute;top:20px;left:20px;
  background:rgba(0,240,255,0.1);border:1px solid var(--neon-cyan);
  color:var(--neon-cyan);padding:10px 18px;border-radius:8px;
  font-family:inherit;font-weight:700;cursor:pointer;transition:0.3s
}
.admin-btn:hover{
  background:rgba(0,240,255,0.2);box-shadow:var(--glow-cyan);
  transform:scale(1.05)
}
.logo{
  font-family:'Orbitron',sans-serif;font-size:clamp(2rem,6vw,4rem);font-weight:900;
  background:linear-gradient(90deg, var(--neon-cyan), var(--neon-purple), var(--neon-pink));
  -webkit-background-clip:text;background-clip:text;color:transparent;
  text-shadow:none;letter-spacing:3px;
  animation:logoPulse 3s ease-in-out infinite
}
@keyframes logoPulse{
  0%,100%{filter:drop-shadow(0 0 15px rgba(0,240,255,0.5))}
  50%{filter:drop-shadow(0 0 30px rgba(176,0,255,0.6))}
}
.subhead{color:var(--text-ice-blue);opacity:0.9;margin-top:10px;font-size:1.1rem}

.container{max-width:1200px;margin:0 auto;padding:40px 20px}
.section-title{
  font-family:'Orbitron',sans-serif;font-size:1.6rem;margin-bottom:30px;
  color:var(--neon-cyan);display:flex;align-items:center;gap:12px
}
.section-title::after{
  content:'';flex:1;height:1px;
  background:linear-gradient(90deg, rgba(0,240,255,0.4), transparent)
}

/* ========== کارت‌های دسته‌بندی سه‌بعدی ========== */
.cats-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(290px,1fr));gap:25px}
.cat-card{
  background:rgba(26,0,51,0.6);backdrop-filter:blur(20px);
  border:1px solid rgba(0,240,255,0.3);border-radius:20px;padding:28px;
  cursor:pointer;transition:0.4s cubic-bezier(0.4,0,0.2,1);
  transform:perspective(1000px) rotateX(0deg) rotateY(0deg)
}
.cat-card:hover{
  transform:perspective(1000px) rotateX(5deg) rotateY(-5deg) translateY(-10px);
  border-color:var(--neon-purple);box-shadow:var(--glow-purple), 0 20px 60px rgba(0,0,0,0.6);
  background:rgba(26,0,51,0.8)
}
.cat-icon{font-size:3rem;margin-bottom:15px}
.cat-name{font-family:'Orbitron',sans-serif;font-size:1.25rem;color:var(--neon-cyan);margin-bottom:8px}
.cat-desc{color:var(--text-ice-blue);opacity:0.8;line-height:1.7;margin-bottom:12px}
.cat-count{
  display:inline-block;padding:4px 12px;border-radius:20px;
  background:rgba(0,255,136,0.15);color:var(--neon-green);font-size:0.85px
}
.empty-msg{text-align:center;padding:60px 20px;color:#444;font-size:1.1rem}

/* ========== صفحه داخلی ========== */
.back-btn{
  display:inline-flex;align-items:center;gap:8px;color:var(--neon-cyan);
  text-decoration:none;margin-bottom:25px;cursor:pointer;transition:0.2s;font-weight:700
}
.back-btn:hover{color:var(--neon-pink);transform:translateX(-5px)}
.item-card{
  background:rgba(26,0,51,0.5);border:1px solid rgba(0,240,255,0.2);
  border-radius:16px;padding:24px;margin-bottom:20px;transition:0.3s
}
.item-card:hover{border-color:rgba(255,0,229,0.4);background:rgba(26,0,51,0.7)}
.item-title{font-size:1.2rem;font-weight:700;color:var(--text-ice);margin-bottom:10px}
.item-img{max-width:100%;border-radius:10px;margin:12px 0;max-height:250px;object-fit:cover}
.item-body{color:var(--text-ice-blue);line-height:1.8;margin-bottom:15px;white-space:pre-wrap}
.item-link{
  display:inline-flex;align-items:center;gap:8px;
  background:linear-gradient(90deg, var(--neon-cyan), var(--neon-purple));
  color:#000;padding:10px 24px;border-radius:10px;text-decoration:none;font-weight:700;
  transition:0.3s
}
.item-link:hover{box-shadow:var(--glow-purple);transform:scale(1.05)}
.hidden{display:none}

/* ========== پنل مدیریت ========== */
.admin-overlay{
  position:fixed;inset:0;background:rgba(0,0,0,0.92);z-index:999;
  display:none;align-items:center;justify-content:center;padding:20px
}
.admin-overlay.active{display:flex}
.admin-box{
  background:linear-gradient(135deg, #0a0e27, #1a0033);
  border:2px solid var(--neon-cyan);border-radius:20px;padding:30px;
  max-width:520px;width:100%;max-height:90vh;overflow-y:auto;
  box-shadow:var(--glow-purple)
}
.admin-box h2{
  text-align:center;font-family:'Orbitron',sans-serif;
  color:var(--neon-cyan);margin-bottom:25px
}
.inp{
  width:100%;padding:14px 16px;margin:8px 0;border-radius:10px;
  border:1px solid rgba(0,240,255,0.3);background:rgba(0,0,0,0.5);
  color:#FFF;font-size:1rem;font-family:inherit
}
.inp:focus{outline:none;border-color:var(--neon-purple);box-shadow:0 0 15px rgba(176,0,255,0.3)}
.btn{
  padding:13px 22px;border-radius:10px;border:none;font-weight:700;
  cursor:pointer;font-family:inherit;transition:0.3s;margin:6px
}
.btn-primary{
  background:linear-gradient(90deg, var(--neon-cyan), var(--neon-purple));
  color:#000;width:100%;margin-top:10px;font-size:1rem
}
.btn-primary:hover{box-shadow:var(--glow-purple);transform:scale(1.02)}
.btn-secondary{background:transparent;border:1px solid var(--neon-cyan);color:var(--neon-cyan)}
.btn-danger{background:transparent;border:1px solid var(--neon-red);color:var(--neon-red)}
.tabs{display:flex;gap:10px;margin-bottom:20px;flex-wrap:wrap}
.tab{
  padding:10px 16px;border-radius:8px;border:1px solid rgba(0,240,255,0.25);
  cursor:pointer;color:#888;transition:0.2s;font-size:0.9rem
}
.tab.active{background:rgba(0,240,255,0.15);border-color:var(--neon-cyan);color:var(--neon-cyan)}
.tab-page{display:none}
.tab-page.active{display:block}
.code-box{
  background:#000;border:1px solid #222;border-radius:10px;padding:18px;
  font-family:monospace;font-size:0.8rem;white-space:pre-wrap;word-break:break-all;
  color:#9f9;max-height:300px;overflow:auto;margin-top:15px;line-height:1.6
}
.list-item{
  padding:12px;border-bottom:1px solid rgba(0,240,255,0.1);
  display:flex;justify-content:space-between;align-items:center;gap:10px;flex-wrap:wrap
}
footer{
  text-align:center;padding:30px 20px;margin-top:60px;
  border-top:1px solid rgba(0,240,255,0.1);color:#444;font-size:0.85rem
}
</style>
</head>
<body>
<div class="bg-layer-1"></div>
<div class="bg-layer-2"></div>
<div class="scanline"></div>
<div id="particles"></div>

<div class="page-wrap">
<header>
  <button class="admin-btn" onclick="openPanel()">⚙️ مدیریت</button>
  <h1 class="logo">VORTEXPLAY</h1>
  <p class="subhead">سامانه گیمینگ سایبرپانک — نسخه نهایی</p>
</header>

<div class="container">
  <!-- صفحه اصلی -->
  <div id="home">
    <h2 class="section-title">دسته‌بندی‌ها</h2>
    <div id="cats-container" class="cats-grid"></div>
  </div>

  <!-- صفحه دسته -->
  <div id="cat-page" class="hidden">
    <span class="back-btn" onclick="goBack()">← بازگشت به صفحه اصلی</span>
    <h2 id="cat-name" class="section-title"></h2>
    <p id="cat-desc" style="color:#66e0ff;margin-bottom:25px"></p>
    <div id="items-container"></div>
  </div>
</div>

<footer>
  VORTEXPLAY © 2026 | سایبرپانک Edition | هاست دائمی گیت‌هاب
</footer>
</div>

<!-- پنل مدیریت -->
<div id="admin-panel" class="admin-overlay">
  <div class="admin-box">
    <h2>🔐 پنل مدیریت</h2>
    
    <div id="login-view">
      <input type="password" id="pass-inp" class="inp" placeholder="رمز ۳۲ رقمی را وارد کنید">
      <button class="btn btn-primary" onclick="checkPass()">ورود</button>
    </div>

    <div id="admin-view" style="display:none">
      <div class="tabs">
        <div class="tab active" data-tab="cats">📂 دسته‌بندی</div>
        <div class="tab" data-tab="items">📄 افزودن محتوا</div>
        <div class="tab" data-tab="code">💻 کد نهایی</div>
      </div>

      <!-- تب دسته‌بندی -->
      <div class="tab-page active" id="tab-cats">
        <h4 style="color:var(--neon-cyan);margin-bottom:12px">ایجاد دسته جدید</h4>
        <input type="text" id="new-cat-name" class="inp" placeholder="نام دسته">
        <input type="text" id="new-cat-desc" class="inp" placeholder="توضیح کوتاه">
        <input type="text" id="new-cat-icon" class="inp" placeholder="آیکون 🎮 یا لینک عکس">
        <button class="btn btn-primary" onclick="addCat()">✅ ایجاد</button>
        <div id="cat-list" style="margin-top:20px"></div>
      </div>

      <!-- تب محتوا -->
      <div class="tab-page" id="tab-items">
        <h4 style="color:var(--neon-cyan);margin-bottom:12px">افزودن پیام / فایل</h4>
        <select id="sel-cat" class="inp">
          <option value="">انتخاب دسته مقصد...</option>
        </select>
        <input type="text" id="item-title" class="inp" placeholder="عنوان">
        <textarea id="item-body" class="inp" rows="4" placeholder="متن و توضیحات"></textarea>
        <input type="text" id="item-img" class="inp" placeholder="لینک عکس (اختیاری)">
        <input type="text" id="item-link" class="inp" placeholder="لینک دانلود (اختیاری)">
        <button class="btn btn-primary" onclick="addItem()">✅ افزودن</button>
      </div>

      <!-- تب کد -->
      <div class="tab-page" id="tab-code">
        <h4 style="color:var(--neon-cyan);margin-bottom:12px">کد کامل برای گیت‌هاب</h4>
        <p style="color:#666;font-size:0.9rem;margin-bottom:10px">کد زیر را کپی کن و جای کل فایل index.html در گیت‌هاب قرار بده:</p>
        <div class="code-box" id="full-code">در حال ساخت کد...</div>
        <button class="btn btn-secondary" style="margin-top:10px;width:100%" onclick="copyCode()">📋 کپی کامل کد</button>
      </div>

      <button class="btn btn-secondary" style="margin-top:20px;width:100%" onclick="closePanel()">بستن</button>
    </div>
  </div>
</div>

<script>
const ADMIN_PASS = "K9#mP2$xR7!vL3@nQ5&bT1*wZ8%yA4^";
let data = {categories:[]};
let activeCat = null;

// ساخت ذرات پس‌زمینه
function createParticles(){
  const cont = document.getElementById('particles');
  const colors = ['p-cyan','p-pink','p-purple'];
  for(let i=0;i<30;i++){
    const p = document.createElement('div');
    p.className = `particle ${colors[Math.floor(Math.random()*colors.length)]}`;
    p.style.left = `${Math.random()*100}%`;
    p.style.animationDelay = `${Math.random()*15}s`;
    cont.appendChild(p);
  }
}

// بارگذاری
function load(){
  createParticles();
  const s = localStorage.getItem('vortex_data');
  if(s) data = JSON.parse(s);
  renderCats();
}
function save(){
  localStorage.setItem('vortex_data', JSON.stringify(data));
  updateCodeBox();
}

// پنل
function openPanel(){
  document.getElementById('admin-panel').classList.add('active');
  document.getElementById('login-view').style.display='block';
  document.getElementById('admin-view').style.display='none';
  document.getElementById('pass-inp').value='';
}
function closePanel(){
  document.getElementById('admin-panel').classList.remove('active');
  activeCat = null;
}
function checkPass(){
  if(document.getElementById('pass-inp').value === ADMIN_PASS){
    document.getElementById('login-view').style.display='none';
    document.getElementById('admin-view').style.display='block';
    renderCatSelect();
    renderCatList();
    updateCodeBox();
  }else alert('❌ رمز اشتباه!');
}

// تب‌ها
document.querySelectorAll('.tab').forEach(t=>{
  t.onclick=()=>{
    document.querySelectorAll('.tab').forEach(x=>x.classList.remove('active'));
    document.querySelectorAll('.tab-page').forEach(x=>x.classList.remove('active'));
    t.classList.add('active');
    document.getElementById('tab-'+t.dataset.tab).classList.add('active');
    if(t.dataset.tab==='code') updateCodeBox();
  }
});

// دسته‌بندی
function addCat(){
  const name = document.getElementById('new-cat-name').value.trim();
  const desc = document.getElementById('new-cat-desc').value.trim();
  const icon = document.getElementById('new-cat-icon').value.trim() || '📁';
  if(!name) return alert('نام دسته را بنویسید');
  data.categories.push({name,desc,icon,items:[]});
  save();renderCats();renderCatSelect();renderCatList();
  document.getElementById('new-cat-name').value='';
  document.getElementById('new-cat-desc').value='';
  document.getElementById('new-cat-icon').value='';
}
function renderCats(){
  const c = document.getElementById('cats-container');
  if(!data.categories.length){
    c.innerHTML='<p class="empty-msg">هنوز دسته‌ای تعریف نشده ⚙️ از پنل مدیریت ایجاد کنید</p>';
    return;
  }
  c.innerHTML = data.categories.map((cat,i)=>`
    <div class="cat-card" onclick="openCat(${i})">
      <div class="cat-icon">${cat.icon}</div>
      <h3 class="cat-name">${cat.name}</h3>
      <p class="cat-desc">${cat.desc || 'مشاهده محتوا'}</p>
      <span class="cat-count">${cat.items.length} مورد</span>
    </div>
  `).join('');
}
function openCat(i){
  activeCat = i;
  document.getElementById('home').classList.add('hidden');
  document.getElementById('cat-page').classList.remove('hidden');
  const cat = data.categories[i];
  document.getElementById('cat-name').textContent = cat.icon+' '+cat.name;
  document.getElementById('cat-desc').textContent = cat.desc;
  renderItems(cat.items);
}
function goBack(){
  activeCat = null;
  document.getElementById('home').classList.remove('hidden');
  document.getElementById('cat-page').classList.add('hidden');
}
function renderItems(items){
  const c = document.getElementById('items-container');
  if(!items.length){
    c.innerHTML='<p class="empty-msg">هنوز محتوایی قرار نگرفته ✨</p>';
    return;
  }
  c.innerHTML = items.map(item=>`
    <div class="item-card">
      <h4 class="item-title">${item.title}</h4>
      ${item.img?`<img src="${item.img}" class="item-img" alt="">`:''}
      <div class="item-body">${item.body}</div>
      ${item.link?`<a href="${item.link}" target="_blank" class="item-link">🔗 دریافت فایل</a>`:''}
    </div>
  `).join('');
}
function renderCatSelect(){
  const sel = document.getElementById('sel-cat');
  sel.innerHTML = '<option value="">انتخاب دسته مقصد...</option>' +
    data.categories.map((cat,i)=>`<option value="${i}">${cat.icon} ${cat.name}</option>`).join('');
}
function renderCatList(){
  const l = document.getElementById('cat-list');
  if(!data.categories.length){l.innerHTML='<p style="opacity:0.6">هنوز دسته‌ای وجود ندارد</p>';return}
  l.innerHTML = data.categories.map((cat,i)=>`
    <div class="list-item">
      <span>${cat.icon} ${cat.name} (${cat.items.length})</span>
      <button class="btn btn-danger" style="padding:6px 12px;font-size:0.8rem" onclick="delCat(${i})">حذف</button>
    </div>
  `).join('');
}
function delCat(i){
  if(confirm('مطمئن هستید؟ تمام محتوای این دسته حذف می‌شود')){
    data.categories.splice(i,1);
    save();renderCats();renderCatSelect();renderCatList();
    if(activeCat===i) goBack();
  }
}

// افزودن آیتم
function addItem(){
  const idx = parseInt(document.getElementById('sel-cat').value);
  const title = document.getElementById('item-title').value.trim();
  const body = document.getElementById('item-body').value.trim();
  const img = document.getElementById('item-img').value.trim();
  const link = document.getElementById('item-link').value.trim();
  if(isNaN(idx) || !title) return alert('دسته و عنوان را تکمیل کنید');
  data.categories[idx].items.push({title,body,img,link});
  save();renderCatList();
  if(activeCat===idx) renderItems(data.categories[idx].items);
  alert('✅ اضافه شد! به تب «کد نهایی» برو');
  document.getElementById('item-title').value='';
  document.getElementById('item-body').value='';
  document.getElementById('item-img').value='';
  document.getElementById('item-link').value='';
}

// تولید کد کامل استاتیک برای گیت‌هاب
function updateCodeBox(){
  document.getElementById('full-code').textContent = generateStaticHTML();
}
function generateStaticHTML(){
  const d = JSON.stringify(data);
  return `<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY 🎮 | Cyberpunk Edition</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{--neon-cyan:#00f0ff;--neon-pink:#ff00e5;--neon-purple:#b000ff;--neon-green:#00ff88;--neon-orange:#ff6600;--neon-yellow:#ffee00;--neon-red:#ff0055;--bg-black:#000;--bg-navy:#0a0e27;--bg-deep-purple:#1a0033;--bg-ink:#000814;--text-ice:#e0f7ff;--text-ice-blue:#b0e0ff;--text-silver:#c0c0c0;--text-gold:#ffd700;--glow-cyan:0 0 10px #00f0ff,0 0 20px #00f0ff,0 0 40px #00f0ff;--glow-pink:0 0 10px #ff00e5,0 0 20px #ff00e5,0 0 40px #ff00e5;--glow-purple:0 0 10px #b000ff,0 0 20px #b000ff,0 0 40px #b000ff;--glow-green:0 0 10px #00ff88,0 0 20px #00ff88,0 0 40px #00ff88}
body{font-family:'Tajawal',sans-serif;min-height:100vh;background:radial-gradient(ellipse at top,#1a0033 0%,transparent 50%),radial-gradient(ellipse at bottom,#0a0e27 0%,transparent 50%),linear-gradient(180deg,#000 0%,#000814 100%);color:var(--text-ice);overflow-x:hidden}
.bg-layer-2{position:fixed;inset:0;background:linear-gradient(90deg,rgba(0,240,255,0.03)1px,transparent 1px),linear-gradient(rgba(0,240,255,0.03)1px,transparent 1px);background-size:60px 60px;transform:perspective(500px)rotateX(60deg);transform-origin:center top;mask-image:linear-gradient(to top,rgba(0,0,0,0.8),transparent);-webkit-mask-image:linear-gradient(to top,rgba(0,0,0,0.8),transparent);opacity:0.4;pointer-events:none;z-index:0}
.scanline{position:fixed;top:0;left:0;width:100%;height:2px;background:linear-gradient(90deg,transparent,#00f0ff,transparent);box-shadow:var(--glow-cyan);animation:scan 8s linear infinite;pointer-events:none;z-index:999;opacity:0.3}
@keyframes scan{0%{transform:translateY(0)}100%{transform:translateY(100vh)}}
.page-wrap{position:relative;z-index:1}
header{position:relative;padding:30px 20px;text-align:center;border-bottom:1px solid rgba(0,240,255,0.2);background:linear-gradient(180deg,rgba(0,240,255,0.08)0%,transparent 100%)}
.logo{font-family:'Orbitron',sans-serif;font-size:clamp(2rem,6vw,4rem);font-weight:900;background:linear-gradient(90deg,#00f0ff,#b000ff,#ff00e5);-webkit-background-clip:text;background-clip:text;color:transparent;letter-spacing:3px;animation:logoPulse 3s ease-in-out infinite}
@keyframes logoPulse{0%,100%{filter:drop-shadow(0 0 15px rgba(0,240,255,0.5))}50%{filter:drop-shadow(0 0 30px rgba(176,0,255,0.6))}}
.subhead{color:var(--text-ice-blue);opacity:0.9;margin-top:10px;font-size:1.1rem}
.container{max-width:1200px;margin:0 auto;padding:40px 20px}
.section-title{font-family:'Orbitron',sans-serif;font-size:1.6rem;margin-bottom:30px;color:var(--neon-cyan);display:flex;align-items:center;gap:12px}
.section-title::after{content:'';flex:1;height:1px;background:linear-gradient(90deg,rgba(0,240,255,0.4),transparent)}
.cats-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(290px,1fr));gap:25px}
.cat-card{background:rgba(26,0,51,0.6);backdrop-filter:blur(20px);border:1px solid rgba(0,240,255,0.3);border-radius:20px;padding:28px;cursor:pointer;transition:0.4s cubic-bezier(0.4,0,0.2,1);transform:perspective(1000px)rotateX(0deg)rotateY(0deg)}
.cat-card:hover{transform:perspective(1000px)rotateX(5deg)rotateY(-5deg)translateY(-10px);border-color:var(--neon-purple);box-shadow:var(--glow-purple),0 20px 60px rgba(0,0,0,0.6);background:rgba(26,0,51,0.8)}
.cat-icon{font-size:3rem;margin-bottom:15px}
.cat-name{font-family:'Orbitron',sans-serif;font-size:1.25rem;color:var(--neon-cyan);margin-bottom:8px}
.cat-desc{color:var(--text-ice-blue);opacity:0.8;line-height:1.7;margin-bottom:12px}
.cat-count{display:inline-block;padding:4px 12px;border-radius:20px;background:rgba(0,255,136,0.15);color:var(--neon-green);font-size:0.85rem}
.hidden{display:none}
.back-btn{display:inline-flex;align-items:center;gap:8px;color:var(--neon-cyan);text-decoration:none;margin-bottom:25px;cursor:pointer;transition:0.2s;font-weight:700}
.back-btn:hover{color:var(--neon-pink);transform:translateX(-5px)}
.item-card{background:rgba(26,0,51,0.5);border:1px solid rgba(0,240,255,0.2);border-radius:16px;padding:24px;margin-bottom:20px;transition:0.3s}
.item-card:hover{border-color:rgba(255,0,229,0.4);background:rgba(26,0,51,0.7)}
.item-title{font-size:1.2rem;font-weight:700;color:var(--text-ice);margin-bottom:10px}
.item-img{max-width:100%;border-radius:10px;margin:12px 0;max-height:250px;object-fit:cover}
.item-body{color:var(--text-ice-blue);line-height:1.8;margin-bottom:15px;white-space:pre-wrap}
.item-link{display:inline-flex;align-items:center;gap:8px;background:linear-gradient(90deg,#00f0ff,#b000ff);color:#000;padding:10px 24px;border-radius:10px;text-decoration:none;font-weight:700;transition:0.3s}
.item-link:hover{box-shadow:var(--glow-purple);transform:scale(1.05)}
.empty-msg{text-align:center;padding:60px 20px;color:#444;font-size:1.1rem}
footer{text-align:center;padding:30px 20px;margin-top:60px;border-top:1px solid rgba(0,240,255,0.1);color:#444;font-size:0.85rem}
</style>
</head>
<body>
<div class="bg-layer-2"></div>
<div class="scanline"></div>
<div class="page-wrap">
<header>
  <h1 class="logo">VORTEXPLAY</h1>
  <p class="subhead">سامانه گیمینگ سایبرپانک</p>
</header>
<div class="container" id="static-content">
  <h2 class="section-title">دسته‌بندی‌ها</h2>
  <div class="cats-grid">
    \${DATA.categories.length===0?'<p class=\"empty-msg\">هنوز محتوایی قرار نگرفته ✨</p>':DATA.categories.map((cat,i)=>\`
      <div class=\"cat-card\" onclick=\"openCat(\${i})\">
        <div class=\"cat-icon\">\${cat.icon}</div>
        <h3 class=\"cat-name\">\${cat.name}</h3>
        <p class=\"cat-desc\">\${cat.desc || 'مشاهده محتوا'}</p>
        <span class=\"cat-count\">\${cat.items.length} مورد</span>
      </div>
    \`).join('')}
  </div>
</div>
<footer>VORTEXPLAY © 2026 | سایبرپانک Edition</footer>
</div>
<script>
const DATA = ${d};
function openCat(i){
  const cat = DATA.categories[i];
  document.getElementById('static-content').innerHTML = \`
    <span class=\"back-btn\" onclick=\"location.reload()\">← بازگشت</span>
    <h2 class=\"section-title\">\${cat.icon} \${cat.name}</h2>
    <p style=\"color:#66e0ff;margin-bottom:25px\">\${cat.desc}</p>
    \${cat.items.length===0?'<p class=\"empty-msg\">هنوز محتوایی قرار نگرفته ✨</p>':cat.items.map(item=>\`
      <div class=\"item-card\">
        <h4 class=\"item-title\">\${item.title}</h4>
        \${item.img?\`<img src=\"\${item.img}\" class=\"item-img\" alt=\"\">\`:''}
        <div class=\"item-body\">\${item.body}</div>
        \${item.link?\`<a href=\"\${item.link}\" target=\"_blank\" class=\"item-link\">🔗 دریافت فایل</a>\`:''}
      </div>
    \`).join('')}
  \`;
}
</script>
</body>
</html>`;
}
function copyCode(){
  const code = document.getElementById('full-code').textContent;
  navigator.clipboard.writeText(code).then(()=>{
    alert('✅ کد کامل کپی شد! در گیت‌هاب جایگزین کن و ذخیره کن');
  }).catch(()=>alert('کپی نشد — دستی انتخاب و کپی کن'));
}

// شروع
document.addEventListener('DOMContentLoaded', load);
</script>
</body>
</html>
