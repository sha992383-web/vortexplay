<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY 👑</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{font-family:Tahoma,SegoeUI,sans-serif;min-height:100vh;color:#f5e6a3;overflow-x:hidden;
    background:radial-gradient(circle at 50% 0%,rgba(212,175,55,.25),transparent 60%),
               radial-gradient(circle at 20% 80%,rgba(75,0,130,.4),transparent 50%),
               linear-gradient(160deg,#0d0618 0%,#2d1b4e 45%,#1a0b2e 100%);
    background-attachment:fixed;padding-bottom:90px}
body.has-bg{background-size:cover;background-position:center}
.particles{position:fixed;inset:0;pointer-events:none;z-index:1;overflow:hidden}
.particle{position:absolute;width:4px;height:4px;background:#ffd700;border-radius:50%;animation:fp 15s infinite;opacity:.6}
@keyframes fp{0%{transform:translateY(100vh) rotate(0);opacity:0}10%{opacity:.6}90%{opacity:.6}100%{transform:translateY(-100vh) rotate(720deg);opacity:0}}
header{position:relative;z-index:10;padding:40px 20px 20px;text-align:center}
.crown{font-size:34px;display:block;margin-bottom:8px;filter:drop-shadow(0 0 15px #ffd700);animation:float 3s ease-in-out infinite}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
.logo-ring{position:relative;display:inline-block;margin-bottom:20px}
.logo-ring::before{content:'';position:absolute;inset:-8px;border-radius:50%;
    background:conic-gradient(from 0deg,#ffd700,#b8860b,#fff2b0,#d4af37,#8b6914,#ffd700);
    animation:spin 5s linear infinite}
.logo-ring::after{content:'';position:absolute;inset:-8px;border-radius:50%;
    background:conic-gradient(from 0deg,#ffd700,#b8860b,#fff2b0,#d4af37,#8b6914,#ffd700);
    animation:spin 5s linear infinite;filter:blur(18px);opacity:.8}
@keyframes spin{to{transform:rotate(360deg)}}
.logo{position:relative;z-index:1;width:160px;height:160px;border-radius:50%;
    border:4px solid #ffd700;box-shadow:0 0 40px rgba(255,215,0,.5);background:#1a0b2e;
    display:flex;align-items:center;justify-content:center;font-size:40px;font-weight:bold;color:#ffd700}
h1{font-size:clamp(28px,7vw,42px);letter-spacing:3px;font-weight:bold;
    color:#ffd700;text-shadow:0 0 20px #ffd700,0 0 40px rgba(255,215,0,.3)}
.sub{font-size:14px;letter-spacing:2px;margin:10px 0 25px;color:#d4af37}
.hero{width:95%;max-width:440px;border-radius:20px;margin:0 auto 35px;display:none;
    border:4px solid #ffd700;box-shadow:0 0 40px rgba(255,215,0,.4),0 15px 50px rgba(0,0,0,.5)}
.menu{max-width:550px;margin:0 auto;padding:0 20px 50px;display:grid;grid-template-columns:repeat(2,1fr);gap:20px;position:relative;z-index:10}
.bw{border-radius:18px;padding:3px;
    background:conic-gradient(from 0deg,#ffd700,#b8860b,#fff2b0,#d4af37,#8b6914,#ffd700);
    animation:hue 6s linear infinite;box-shadow:0 5px 25px rgba(255,215,0,.25)}
@keyframes hue{to{filter:hue-rotate(360deg)}}
.btn{display:flex;flex-direction:column;align-items:center;justify-content:center;padding:30px 15px;
    border-radius:16px;color:#f5e6a3;background:rgba(26,11,46,.8);backdrop-filter:blur(12px);
    border:2px solid rgba(255,215,0,.5);cursor:pointer;transition:.3s}
.btn:active{transform:scale(.95)}
.btn .ic{font-size:42px;margin-bottom:8px;filter:drop-shadow(0 0 12px #ffd700)}
.btn .nm{font-size:15px;font-weight:bold;letter-spacing:1px;color:#ffd700}
.btn .ct{color:#d4af37;font-size:12px;margin-top:5px}
.admin-bar{position:fixed;bottom:0;left:0;right:0;background:linear-gradient(90deg,#0d0618,#2d1b4e,#0d0618);
    border-top:3px solid #ffd700;padding:15px 20px;z-index:100;
    box-shadow:0 -5px 30px rgba(255,215,0,.3);backdrop-filter:blur(10px)}
.admin-btn{display:flex;align-items:center;justify-content:center;gap:10px;
    background:linear-gradient(90deg,#ffd700,#b8860b);color:#1a0b2e;border:none;
    padding:12px 25px;border-radius:12px;font-weight:bold;font-size:14px;cursor:pointer;
    width:100%;max-width:400px;margin:0 auto;
    box-shadow:0 0 20px rgba(255,215,0,.5);transition:.3s}
.admin-btn:active{transform:scale(.97)}
.modal{display:none;position:fixed;inset:0;background:rgba(0,0,0,.85);z-index:1000;overflow-y:auto;padding:20px}
.modal.active{display:block}
.modal-content{max-width:720px;margin:20px auto;background:linear-gradient(160deg,#0d0618,#2d1b4e,#1a0b2e);
    border:2px solid rgba(255,215,0,.4);border-radius:18px;padding:25px}
.modal-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:20px;
    padding-bottom:15px;border-bottom:2px solid rgba(255,215,0,.3)}
.modal-title{color:#ffd700;font-size:20px;font-weight:bold}
.close-btn{background:linear-gradient(135deg,#ff0066,#ffd700);color:#1a0b2e;border:none;
    padding:8px 16px;border-radius:8px;cursor:pointer;font-weight:bold}
.card{background:rgba(26,11,46,.75);backdrop-filter:blur(10px);border:2px solid rgba(255,215,0,.4);
    border-radius:16px;padding:16px;margin-bottom:15px}
.card img{width:100%;height:190px;object-fit:cover;border-radius:12px;margin-bottom:10px;border:2px solid #ffd700}
.card h3{font-size:17px;margin-bottom:6px;color:#ffd700;font-weight:bold}
.card p{font-size:14px;line-height:1.8;margin-bottom:10px;color:#e8d9a0}
.dl{display:inline-block;padding:10px 20px;border-radius:10px;background:linear-gradient(135deg,#ffd700,#b8860b);
    color:#1a0b2e;text-decoration:none;font-weight:bold;font-size:13px}
.empty{text-align:center;padding:40px 20px;color:#d4af37}
.empty .big{font-size:55px;display:block;margin-bottom:12px}
.form-group{margin-bottom:15px}
label{display:block;color:#d4af37;font-size:13px;margin-bottom:5px}
input,select,textarea{width:100%;padding:11px;border:2px solid rgba(255,215,0,.3);border-radius:8px;
    background:rgba(13,6,24,.7);color:#f5e6a3;font-size:14px}
textarea{min-height:80px;resize:vertical}
input:focus,select:focus,textarea:focus{outline:none;border-color:#ffd700}
.btn-submit{background:linear-gradient(90deg,#ffd700,#b8860b);color:#1a0b2e;border:none;padding:12px 22px;
    border-radius:10px;font-weight:bold;font-size:14px;cursor:pointer;width:100%}
.btn-danger{background:linear-gradient(90deg,#ff0044,#ff0066);color:#fff}
.admin-sec{background:rgba(26,11,46,.8);border:2px solid rgba(255,215,0,.35);border-radius:14px;padding:20px;margin-bottom:20px}
.admin-sec h2{color:#ffd700;font-size:17px;margin-bottom:14px;font-weight:bold}
.admin-item{background:rgba(13,6,24,.6);border:1px solid rgba(255,215,0,.25);border-radius:10px;padding:12px;
    margin-bottom:10px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:8px}
.preview{max-width:120px;max-height:120px;border-radius:10px;border:2px solid #ffd700;margin-top:10px;display:none}
.bg-preview{max-width:200px;border-radius:8px;border:2px solid #ffd700;margin-top:10px;display:none}
.login-card{max-width:360px;margin:80px auto;text-align:center;padding:35px;
    background:rgba(26,11,46,.9);border:2px solid rgba(255,215,0,.5);border-radius:18px}
.err{color:#ff5577;font-size:13px;margin-bottom:12px}
.toast{position:fixed;top:20px;left:50%;transform:translateX(-50%);background:linear-gradient(90deg,#ffd700,#b8860b);
    color:#1a0b2e;padding:12px 24px;border-radius:10px;font-weight:bold;z-index:9999;opacity:0;transition:.3s;pointer-events:none}
.toast.show{opacity:1}
.loading{text-align:center;padding:40px;color:#ffd700;font-size:18px}
@media(max-width:450px){.menu{grid-template-columns:1fr}.logo{width:130px;height:130px}}
</style>
</head>
<body>

<div class="toast" id="toast"></div>
<div class="particles" id="particles"></div>

<div id="mainPage">
<header>
<span class="crown">👑</span>
<div class="logo-ring">
<div id="logoImg" class="logo">VP</div>
</div>
<h1 id="titleText">VORTEXPLAY</h1>
<div class="sub" id="subtitleText">✦ پایگاه گیمینگ سلطنتی ✦</div>
<img id="heroImg" class="hero" alt="کاور اصلی">
</header>
<main class="menu" id="menuGrid">
<div class="bw"><div class="btn" onclick="openCat('bazi')">
  <div class="ic">🎮</div><div class="nm">بازی‌ها</div><div class="ct" id="cnt-bazi">(0 مورد)</div>
</div></div>
<div class="bw"><div class="btn" onclick="openCat('pelod')">
  <div class="ic">📦</div><div class="nm">پیلود</div><div class="ct" id="cnt-pelod">(0 مورد)</div>
</div></div>
<div class="bw"><div class="btn" onclick="openCat('bakap')">
  <div class="ic">💾</div><div class="nm">بکاپ/آموزش</div><div class="ct" id="cnt-bakap">(0 مورد)</div>
</div></div>
<div class="bw"><div class="btn" onclick="openCat('other')">
  <div class="ic">📁</div><div class="nm">سایر</div><div class="ct" id="cnt-other">(0 مورد)</div>
</div></div>
</main>
</div>

<div class="admin-bar"><button class="admin-btn" onclick="showLogin()">⚙️ پنل مدیریت</button></div>

<div class="modal" id="catModal"><div class="modal-content">
<div class="modal-header"><div class="modal-title" id="catTitle"></div><button class="close-btn" onclick="closeModal('catModal')">✕</button></div>
<div id="catItems"></div>
</div></div>

<div class="modal" id="loginModal"><div class="login-card">
<span class="crown" style="font-size:45px">👑</span>
<h2 style="color:#ffd700;margin:22px 0;font-weight:bold">ورود به پنل</h2>
<div class="err" id="loginErr" style="display:none">❌ رمز اشتباه است!</div>
<input type="password" id="passInput" placeholder="رمز ۳۲ رقمی" style="text-align:center;letter-spacing:2px">
<button class="btn-submit" onclick="doLogin()" style="margin-top:12px">🔓 ورود</button>
<button class="btn-submit" onclick="closeModal('loginModal')" style="margin-top:8px;background:rgba(255,255,255,.1);color:#d4af37">انصراف</button>
</div></div>

<div class="modal" id="adminModal"><div class="modal-content">
<div class="modal-header"><div class="modal-title">👑 پنل مدیریت</div><button class="close-btn" onclick="closeAdmin()">✕</button></div>

<div class="admin-sec"><h2>📝 متن‌ها</h2>
<div class="form-group"><label>عنوان سایت</label><input id="setTitle" value="VORTEXPLAY"></div>
<div class="form-group"><label>زیرعنوان</label><input id="setSubtitle" value="پایگاه گیمینگ سلطنتی"></div>
<button class="btn-submit" onclick="saveTexts()">💾 ذخیره</button>
</div>

<div class="admin-sec"><h2>➕ افزودن محتوا</h2>
<div class="form-group"><label>دسته‌بندی</label>
<select id="msgCat">
<option value="bazi">🎮 بازی‌ها</option>
<option value="pelod">📦 پیلود</option>
<option value="bakap">💾 بکاپ/آموزش</option>
<option value="other">📁 سایر</option>
</select>
</div>
<div class="form-group"><label>عنوان</label><input id="msgTitle" placeholder="عنوان محتوا"></div>
<div class="form-group"><label>توضیحات</label><textarea id="msgDesc" placeholder="توضیحات کوتاه"></textarea></div>
<div class="form-group"><label>لینک دانلود</label><input id="msgLink" type="url" placeholder="https://..."></div>
<div class="form-group"><label>تصویر کاور</label><input type="file" id="msgCover" accept="image/*"></div>
<button class="btn-submit" onclick="addMessage()">✅ ثبت</button>
</div>

<div class="admin-sec"><h2>📋 لیست محتوا</h2><div id="allMsgs"></div></div>

<button class="btn-submit btn-danger" onclick="clearAll()" style="margin-top:10px">🗑 پاک کردن همه</button>
<button class="btn-submit" onclick="exportData()" style="margin-top:10px;background:linear-gradient(90deg,#00cc88,#009966)">📤 گرفتن پشتیبان</button>
<button class="btn-submit" onclick="importData()" style="margin-top:10px;background:linear-gradient(90deg,#4488ff,#2266dd)">📥 بازگرداندن</button>
<input type="file" id="importFile" accept=".json" style="display:none" onchange="readImport(this)">
<button class="btn-submit btn-danger" onclick="logoutAdmin()" style="margin-top:15px">🚪 خروج</button>
</div></div>

<script>
const ADMIN_PASS = 'VORTEX-992383-SHAHRIAR-2026-PLAY-IRAN-GAME';
const STORAGE_KEY = 'vortexplay_data';

let data = {
  title:'VORTEXPLAY',
  subtitle:'پایگاه گیمینگ سلطنتی',
  logo:'', hero:'', bg:'',
  categories:[
    {name:'bazi', display:'بازی‌ها', icon:'🎮'},
    {name:'pelod', display:'پیلود', icon:'📦'},
    {name:'bakap', display:'بکاپ/آموزش', icon:'💾'},
    {name:'other', display:'سایر', icon:'📁'}
  ],
  messages:[]
};
let isAdmin = false;

function showToast(m){
  const t = document.getElementById('toast');
  t.textContent = m; t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 2500);
}

function createParticles(){
  const c = document.getElementById('particles');
  for(let i=0;i<30;i++){
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.left = Math.random()*100+'%';
    p.style.animationDelay = Math.random()*15+'s';
    p.style.animationDuration = (15+Math.random()*10)+'s';
    c.appendChild(p);
  }
}

function saveData(){
  localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
  showToast('✅ ذخیره شد');
  render();
}

function loadData(){
  const saved = localStorage.getItem(STORAGE_KEY);
  if(saved){
    try{ data = JSON.parse(saved); }
    catch{ data = getDefaultData(); }
  }
  render();
}

function getDefaultData(){
  return {
    title:'VORTEXPLAY', subtitle:'پایگاه گیمینگ سلطنتی',
    logo:'', hero:'', bg:'',
    categories:[
      {name:'bazi', display:'بازی‌ها', icon:'🎮'},
      {name:'pelod', display:'پیلود', icon:'📦'},
      {name:'bakap', display:'بکاپ/آموزش', icon:'💾'},
      {name:'other', display:'سایر', icon:'📁'}
    ], messages:[]
  };
}

function render(){
  document.getElementById('titleText').textContent = data.title;
  document.getElementById('subtitleText').textContent = '✦ ' + data.subtitle + ' ✦';
  
  data.categories.forEach(c => {
    const n = data.messages.filter(m => m.cat === c.name).length;
    const el = document.getElementById(`cnt-${c.name}`);
    if(el) el.textContent = `(${n} مورد)`;
  });
  
  if(data.bg){ document.body.style.backgroundImage = `url(${data.bg})`; document.body.classList.add('has-bg'); }
  else { document.body.style.backgroundImage = ''; document.body.classList.remove('has-bg'); }
}

function openCat(n){
  const c = data.categories.find(x => x.name === n);
  if(!c) return;
  document.getElementById('catTitle').textContent = `${c.icon} ${c.display}`;
  const m = data.messages.filter(x => x.cat === n);
  document.getElementById('catItems').innerHTML = !m.length
    ? '<div class="empty"><span class="big">👑</span>هنوز محتوایی اضافه نشده!</div>'
    : m.map((x,i) => `<div class="card">
        ${x.cover?`<img src="${x.cover}" alt="">`:''}
        <h3>${x.title}</h3>
        ${x.desc?`<p>${x.desc}</p>`:''}
        ${x.link?`<a href="${x.link}" target="_blank" class="dl">⬇️ دانلود</a>`:''}
        ${isAdmin?`<br><button class="btn-submit btn-danger" onclick="delMsg(${i})" style="margin-top:10px;padding:6px 12px;font-size:12px;width:auto">🗑 حذف</button>`:''}
      </div>`).join('');
  document.getElementById('catModal').classList.add('active');
}

function closeModal(id){ document.getElementById(id).classList.remove('active'); }

function showLogin(){
  if(isAdmin){ openAdmin(); return; }
  document.getElementById('loginErr').style.display = 'none';
  document.getElementById('passInput').value = '';
  document.getElementById('loginModal').classList.add('active');
}

function doLogin(){
  if(document.getElementById('passInput').value === ADMIN_PASS){
    isAdmin = true; closeModal('loginModal'); openAdmin(); showToast('✅ ورود موفق');
  } else {
    document.getElementById('loginErr').style.display = 'block';
  }
}

function openAdmin(){
  document.getElementById('setTitle').value = data.title;
  document.getElementById('setSubtitle').value = data.subtitle;
  renderMsgList();
  document.getElementById('adminModal').classList.add('active');
}

function closeAdmin(){ closeModal('adminModal'); }
function logoutAdmin(){ isAdmin = false; closeAdmin(); showToast('🚪 خروج موفق'); }

function renderMsgList(){
  document.getElementById('allMsgs').innerHTML = !data.messages.length
    ? '<p style="color:#d4af37;text-align:center">هنوز محتوایی نیست</p>'
    : data.messages.map((m,i) => {
        const c = data.categories.find(x => x.name === m.cat);
        return `<div class="admin-item"><span>${c?c.icon:''} ${m.title}</span>
          <button class="btn-submit btn-danger" onclick="delMsg(${i})" style="width:auto;padding:6px 12px">🗑</button></div>`;
      }).join('');
}

function saveTexts(){
  data.title = document.getElementById('setTitle').value || 'VORTEXPLAY';
  data.subtitle = document.getElementById('setSubtitle').value || 'پایگاه گیمینگ';
  saveData();
}

async function addMessage(){
  const t = document.getElementById('msgTitle').value.trim();
  if(!t) return showToast('عنوان را بنویس!');
  const f = document.getElementById('msgCover').files[0];
  let cover = '';
  if(f){
    const reader = new FileReader();
    await new Promise(r => {
      reader.onload = e => { cover = e.target.result; r(); };
      reader.readAsDataURL(f);
    });
  }
  data.messages.push({
    cat: document.getElementById('msgCat').value,
    title: t,
    desc: document.getElementById('msgDesc').value.trim(),
    link: document.getElementById('msgLink').value.trim(),
    cover: cover
  });
  saveData();
  renderMsgList();
  document.getElementById('msgTitle').value = '';
  document.getElementById('msgDesc').value = '';
  document.getElementById('msgLink').value = '';
  document.getElementById('msgCover').value = '';
  showToast('✅ اضافه شد!');
}

function delMsg(i){
  if(!confirm('مطمئنی حذف بشه؟')) return;
  data.messages.splice(i,1);
  saveData();
  renderMsgList();
}

function clearAll(){
  if(!confirm('همه چیز پاک شود؟ بازگشت ندارد!')) return;
  data.messages = [];
  saveData();
  renderMsgList();
}

function exportData(){
  const blob = new Blob([JSON.stringify(data,null,2)], {type:'application/json'});
  const a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = 'vortexplay-backup.json';
  a.click();
  showToast('✅ پشتیبان گرفته شد');
}

function importData(){
  document.getElementById('importFile').click();
}

function readImport(input){
  const f = input.files[0];
  if(!f) return;
  const r = new FileReader();
  r.onload = e => {
    try{
      const d = JSON.parse(e.target.result);
      if(!d.messages) throw new Error('فرمت نامعتبر');
      if(confirm('محتوای فعلی جایگزین شود؟')){
        data = d;
        saveData();
        renderMsgList();
        showToast('✅ بازگردانده شد');
      }
    }catch{
      showToast('❌ فایل نامعتبر');
    }
  };
  r.readAsText(f);
  input.value = '';
}

createParticles();
loadData();
</script>
</body>
</html>
