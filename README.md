<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEXPLAY | امپراتوری طلایی</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700;900&family=Vazirmatn:wght@400;600;700;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{
    --gold-main:#D4AF37; --gold-bright:#FFD700; --gold-dark:#B8860B;
    --gold-light:#FFF8DC; --gold-glow:rgba(255,215,0,0.4);
    --cream:#FFFDF5; --ivory:#FFFFF0; --soft-gold:#F5F0C9;
    --text-dark:#2C2000; --text-gold:#8B6914;
    --shadow-gold:0 4px 20px rgba(212,175,55,0.25),0 8px 30px rgba(255,215,0,0.15);
    --shadow-soft:0 2px 15px rgba(212,175,55,0.1);
}
body{
    font-family:'Vazirmatn',sans-serif;min-height:100vh;
    background:linear-gradient(180deg,#FFFDF5 0%,#FFF8DC 40%,#F9F2C0 100%);
    color:var(--text-dark);overflow-x:hidden;
}
.particles{position:fixed;inset:0;pointer-events:none;z-index:1}
.sparkle{
    position:absolute;width:6px;height:6px;background:var(--gold-bright);
    border-radius:50%;animation:twinkle 4s ease-in-out infinite;opacity:0
}
@keyframes twinkle{
    0%,100%{opacity:0;transform:scale(0.5)}
    50%{opacity:0.8;transform:scale(1.2)}
}
.header{
    position:fixed;top:0;right:0;left:0;z-index:100;
    background:rgba(255,253,245,0.85);backdrop-filter:blur(12px);
    border-bottom:1px solid rgba(212,175,55,0.25);
    padding:14px 24px;display:flex;justify-content:space-between;align-items:center
}
.logo{
    font-family:'Cinzel',serif;font-size:28px;font-weight:900;
    color:var(--gold-dark);cursor:pointer;letter-spacing:1px;
    text-shadow:0 0 10px var(--gold-glow)
}
.logo span{color:var(--gold-bright)}
.nav-links{display:flex;gap:28px;list-style:none}
.nav-links a{
    color:var(--text-gold);text-decoration:none;font-weight:700;font-size:16px;
    transition:0.3s ease;position:relative
}
.nav-links a:hover{color:var(--gold-bright);text-shadow:0 0 8px var(--gold-glow)}
.admin-btn{
    background:linear-gradient(135deg,var(--gold-bright),var(--gold-dark));
    color:#fff!important;padding:10px 26px;border-radius:50px;font-weight:800;
    box-shadow:var(--shadow-gold);transition:0.3s ease
}
.admin-btn:hover{transform:scale(1.05)}
.hero{
    padding:160px 24px 100px;text-align:center;position:relative;z-index:2
}
.crown-icon{font-size:72px;animation:floatCrown 3s ease-in-out infinite;margin-bottom:15px}
@keyframes floatCrown{
    0%,100%{transform:translateY(0);filter:drop-shadow(0 0 15px var(--gold-bright))}
    50%{transform:translateY(-12px);filter:drop-shadow(0 0 30px var(--gold-bright))}
}
.hero h1{
    font-family:'Cinzel',serif;font-size:clamp(42px,11vw,86px);
    background:linear-gradient(90deg,var(--gold-dark),var(--gold-bright),var(--gold-main));
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;
    margin-bottom:20px;letter-spacing:2px
}
.hero p{font-size:clamp(18px,4vw,26px);color:var(--text-gold);margin-bottom:45px;font-weight:600}
.container{max-width:1200px;margin:0 auto;padding:0 24px;position:relative;z-index:2}
.section{padding:70px 0}
.section-title{
    font-family:'Cinzel',serif;font-size:34px;margin-bottom:45px;text-align:center;
    color:var(--gold-dark);position:relative
}
.section-title::after{
    content:'';position:absolute;bottom:-10px;right:50%;transform:translateX(50%);
    width:100px;height:4px;background:linear-gradient(90deg,transparent,var(--gold-bright),transparent);border-radius:2px
}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(290px,1fr));gap:28px}
.card{
    background:#fff;border-radius:20px;padding:28px;
    border:2px solid rgba(212,175,55,0.2);
    box-shadow:var(--shadow-soft);transition:0.4s ease;cursor:pointer
}
.card:hover{
    transform:translateY(-8px);border-color:var(--gold-bright);
    box-shadow:0 12px 40px rgba(212,175,55,0.25)
}
.card h3{color:var(--gold-dark);margin-bottom:12px;font-size:22px;font-weight:800}
.card p{color:#6B5A1A;font-size:15px;margin-bottom:15px;line-height:1.7}
.card .count{
    display:inline-block;background:var(--soft-gold);color:var(--gold-dark);
    padding:5px 16px;border-radius:20px;font-size:13px;font-weight:700
}
.msg-card{
    background:#fff;border-radius:16px;padding:24px;margin-bottom:20px;
    border-right:4px solid var(--gold-bright);
    box-shadow:var(--shadow-soft);transition:0.3s ease
}
.msg-card:hover{border-right-width:6px;box-shadow:0 4px 20px rgba(212,175,55,0.15)}
.msg-card h4{color:var(--gold-dark);margin-bottom:10px;font-size:19px}
.msg-card time{font-size:13px;color:#A89538;display:block;margin-top:8px}
.btn{
    display:inline-block;padding:14px 36px;border-radius:50px;font-weight:800;
    text-decoration:none;transition:0.3s ease;border:none;cursor:pointer;font-size:17px
}
.btn-gold{
    background:linear-gradient(135deg,var(--gold-bright),var(--gold-dark));
    color:#fff;box-shadow:var(--shadow-gold)
}
.btn-gold:hover{transform:scale(1.08)}
.btn-outline-gold{
    background:transparent;color:var(--gold-dark);border:2px solid var(--gold-main)
}
.btn-outline-gold:hover{background:var(--soft-gold)}
.btn-red{background:linear-gradient(135deg,#E53935,#C62828);color:#fff}
.modal-overlay{
    position:fixed;inset:0;background:rgba(44,32,0,0.6);backdrop-filter:blur(6px);
    z-index:999;display:none;align-items:center;justify-content:center;padding:20px
}
.modal-overlay.active{display:flex}
.modal{
    background:linear-gradient(160deg,#FFFDF5,#FFF8DC);border-radius:24px;
    padding:34px;max-width:520px;width:100%;border:3px solid var(--gold-main);
    box-shadow:0 10px 50px rgba(212,175,55,0.3)
}
.modal h2{color:var(--gold-dark);margin-bottom:24px;text-align:center;font-family:'Cinzel',serif}
.form-group{margin-bottom:20px}
.form-group label{display:block;margin-bottom:8px;color:var(--text-gold);font-weight:700}
.form-group input,.form-group select,.form-group textarea{
    width:100%;padding:14px 18px;background:#fff;
    border:2px solid rgba(212,175,55,0.25);border-radius:12px;color:var(--text-dark);
    font-family:inherit;font-size:15px;transition:0.3s ease
}
.form-group input:focus,.form-group textarea:focus{outline:none;border-color:var(--gold-bright);box-shadow:0 0 0 4px rgba(255,215,0,0.15)}
.modal-buttons{display:flex;gap:12px;margin-top:28px;flex-wrap:wrap}
.modal-buttons .btn{flex:1;min-width:130px;text-align:center;font-size:15px;padding:12px 20px}
.tabs{display:flex;gap:10px;margin-bottom:25px;flex-wrap:wrap}
.tab-btn{
    padding:11px 22px;background:transparent;border:2px solid transparent;
    color:var(--text-gold);border-radius:12px;cursor:pointer;transition:0.3s ease;font-weight:700
}
.tab-btn.active{border-color:var(--gold-bright);background:var(--soft-gold);color:var(--gold-dark)}
.tab-content{display:none}
.tab-content.active{display:block}
.footer{
    text-align:center;padding:45px 20px;color:var(--text-gold);
    border-top:2px solid rgba(212,175,55,0.15);margin-top:70px;font-weight:600
}
.hidden{display:none!important}
</style>
</head>
<body>
<div class="particles" id="stars"></div>

<header class="header">
    <div class="logo" onclick="goHome()">👑 VORTEX<span>PLAY</span></div>
    <ul class="nav-links">
        <li><a href="#" onclick="showSec('home')">خانه</a></li>
        <li><a href="#" onclick="showSec('cats')">دسته‌بندی‌ها</a></li>
        <li><a href="#" onclick="showSec('msgs')">همه پیام‌ها</a></li>
        <li><a href="#" class="admin-btn" onclick="openLogin()">پنل مدیریت</a></li>
    </ul>
</header>

<section class="hero" id="s-home">
    <div class="crown-icon">👑</div>
    <h1>VORTEXPLAY</h1>
    <p>امپراتوری طلایی گیمینگ — جایی که همه چیز درخشان است</p>
    <a href="#" class="btn btn-gold" onclick="showSec('cats')">ورود به قلمرو</a>
</section>

<div class="container">
    <section class="section hidden" id="s-cats">
        <h2 class="section-title">📂 دسته‌بندی‌های طلایی</h2>
        <div class="grid" id="cats-list"></div>
    </section>

    <section class="section hidden" id="s-items">
        <h2 class="section-title" id="cat-name"></h2>
        <div class="grid" id="items-list"></div>
        <br><a href="#" class="btn btn-outline-gold" onclick="showSec('cats')">بازگشت به دسته‌بندی‌ها</a>
    </section>

    <section class="section hidden" id="s-msgs">
        <h2 class="section-title">💬 تمام پیام‌ها و مطالب</h2>
        <div id="msgs-list"></div>
    </section>
</div>

<footer class="footer">
    <p>© ۲۰۲۶ VORTEXPLAY — امپراتوری طلایی. همه حقوق محفوظ است.</p>
</footer>

<!-- مودال‌ها -->
<div class="modal-overlay" id="login-modal">
    <div class="modal">
        <h2>🔐 ورود به پنل مدیریت</h2>
        <div class="form-group">
            <label>رمز عبور ۳۲ رقمی</label>
            <input type="password" id="pass-input" placeholder="رمز را وارد کنید...">
        </div>
        <p id="err-msg" style="color:#D32F2F;display:none">❌ رمز عبور صحیح نیست!</p>
        <div class="modal-buttons">
            <button class="btn btn-gold" onclick="checkPass()">ورود</button>
            <button class="btn btn-outline-gold" onclick="closeModal('login-modal')">بستن</button>
        </div>
    </div>
</div>

<div class="modal-overlay" id="admin-modal">
    <div class="modal" style="max-width:620px">
        <h2>⚙️ پنل مدیریت امپراتوری</h2>
        <div class="tabs">
            <button class="tab-btn active" data-tab="t1">دسته‌بندی</button>
            <button class="tab-btn" data-tab="t2">افزودن پیام</button>
            <button class="tab-btn" data-tab="t3">ذخیره داده‌ها</button>
        </div>

        <div class="tab-content active" id="t1">
            <div class="form-group">
                <label>نام دسته‌بندی جدید</label>
                <input type="text" id="new-cat" placeholder="مثال: بازی‌های پلی‌استیشن">
            </div>
            <button class="btn btn-gold" onclick="addCat()">✅ ساخت دسته جدید</button>
            <br><br>
            <h4 style="color:var(--gold-dark)">لیست دسته‌ها:</h4>
            <div id="manage-cats" style="margin-top:12px"></div>
        </div>

        <div class="tab-content" id="t2">
            <div class="form-group">
                <label>انتخاب دسته‌بندی</label>
                <select id="msg-cat"></select>
            </div>
            <div class="form-group">
                <label>عنوان پیام</label>
                <input type="text" id="msg-title" placeholder="مثال: بهترین بازی‌های سال ۲۰۲۶">
            </div>
            <div class="form-group">
                <label>متن و توضیحات</label>
                <textarea id="msg-body" rows="5" placeholder="توضیحات کامل را بنویسید..."></textarea>
            </div>
            <div class="form-group">
                <label>لینک دانلود (اختیاری)</label>
                <input type="url" id="msg-link" placeholder="https://...">
            </div>
            <button class="btn btn-gold" onclick="saveMsg()">✅ انتشار پیام</button>
        </div>

        <div class="tab-content" id="t3">
            <p style="color:var(--text-gold);margin-bottom:15px;line-height:1.7">کد زیر را کپی کرده و در فایل <code>index.html</code> جایگزین کنید تا همه تغییرات برای همیشه بماند:</p>
            <textarea id="data-code" rows="10" style="font-size:12px;direction:ltr;width:100%;background:#fff"></textarea>
            <div class="modal-buttons">
                <button class="btn btn-gold" onclick="copyData()">📋 کپی کد</button>
                <button class="btn btn-outline-gold" onclick="loadData()">📥 بارگذاری از کد</button>
            </div>
        </div>

        <div class="modal-buttons" style="margin-top:30px">
            <button class="btn btn-red" onclick="exitAdmin()">خروج</button>
            <button class="btn btn-outline-gold" onclick="closeModal('admin-modal')">بستن</button>
        </div>
    </div>
</div>

<script>
// 🔑 رمز پنل مدیریت — می‌توانید تغییر دهید
const ADMIN_KEY = "Vx9Qm7Rp3Lz8Kw2Nf5Ht6Yj4Bc1Ds0Ae";

// داده‌های سایت
let DB = {
    categories: [],
    posts: []
};
let isAdmin = false;
let activeCat = null;

// ایجاد ستاره‌های درخشان پس‌زمینه
function makeStars(){
    const cont = document.getElementById('stars');
    for(let i=0;i<60;i++){
        const s = document.createElement('div');
        s.className = 'sparkle';
        s.style.left = Math.random()*100+'%';
        s.style.top = Math.random()*100+'%';
        s.style.animationDelay = Math.random()*4+'s';
        cont.appendChild(s);
    }
}

// نمایش بخش‌ها
function showSec(id){
    document.querySelectorAll('.section').forEach(s=>s.classList.add('hidden'));
    document.getElementById('s-'+id).classList.remove('hidden');
    if(id==='cats') renderCats();
    if(id==='msgs') renderAllMsgs();
    window.scrollTo({top:0,behavior:'smooth'});
}
function goHome(){showSec('home')}

// باز و بسته کردن مودال‌ها
function openLogin(){document.getElementById('login-modal').classList.add('active')}
function closeModal(id){document.getElementById(id).classList.remove('active')}

// بررسی رمز
function checkPass(){
    const input = document.getElementById('pass-input').value.trim();
    if(input===ADMIN_KEY){
        isAdmin=true;
        closeModal('login-modal');
        openAdmin();
    }else{
        document.getElementById('err-msg').style.display='block';
    }
}

function openAdmin(){
    document.getElementById('admin-modal').classList.add('active');
    renderManageCats();
    fillCatSelect();
    setupTabs();
    updateExport();
}

function setupTabs(){
    document.querySelectorAll('.tab-btn').forEach(btn=>{
        btn.onclick=()=>{
            document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(c=>c.classList.remove('active'));
            btn.classList.add('active');
            document.getElementById(btn.dataset.tab).classList.add('active');
        };
    });
}

// مدیریت دسته‌بندی‌ها
function addCat(){
    const name = document.getElementById('new-cat').value.trim();
    if(!name) return alert('⚠️ نام دسته را بنویسید!');
    DB.categories.push({id:'cat_'+Date.now(),name});
    document.getElementById('new-cat').value='';
    renderManageCats();
    renderCats();
    fillCatSelect();
    updateExport();
}

function delCat(id){
    if(!confirm('آیا مطمئن هستید؟ تمام پیام‌های این دسته نیز حذف می‌شوند!')) return;
    DB.categories = DB.categories.filter(c=>c.id!==id);
    DB.posts = DB.posts.filter(p=>p.catId!==id);
    renderManageCats();
    renderCats();
    fillCatSelect();
    updateExport();
}

function renderManageCats(){
    const cont = document.getElementById('manage-cats');
    cont.innerHTML = DB.categories.length===0 ? '<p style="color:var(--text-gold)">هنوز دسته‌ای تعریف نشده</p>' :
        DB.categories.map(c=>`
            <div style="display:flex;justify-content:space-between;align-items:center;padding:12px;background:${var(--soft-gold)};border-radius:10px;margin-bottom:8px">
                <span style="color:var(--gold-dark);font-weight:700">${c.name}</span>
                <button class="btn btn-red" style="padding:6px 14px;font-size:13px" onclick="delCat('${c.id}')">حذف</button>
            </div>
        `).join('');
}

function renderCats(){
    const cont = document.getElementById('cats-list');
    cont.innerHTML = DB.categories.length===0 ? '<p style="color:var(--text-gold);grid-column:1/-1;text-align:center;padding:30px">هنوز دسته‌ای وجود ندارد — وارد پنل مدیریت شوید</p>' :
        DB.categories.map(c=>{
            const count = DB.posts.filter(p=>p.catId===c.id).length;
            return `
                <div class="card" onclick="openCat('${c.id}')">
                    <h3>${c.name}</h3>
                    <p>مشاهده تمام پیام‌ها، فایل‌ها و لینک‌های دانلود</p>
                    <span class="count">${count} مورد</span>
                </div>
            `;
        }).join('');
}

function openCat(catId){
    activeCat = catId;
    const cat = DB.categories.find(c=>c.id===catId);
    document.getElementById('cat-name').textContent = cat.name;
    renderItems();
    showSec('items');
}

function renderItems(){
    const cont = document.getElementById('items-list');
    const list = DB.posts.filter(p=>p.catId===activeCat);
    cont.innerHTML = list.length===0 ? '<p style="color:var(--text-gold);grid-column:1/-1;text-align:center;padding:30px">هنوز پیامی در این دسته قرار نگرفته</p>' :
        list.map(item=>`
            <div class="card">
                <h3>${item.title}</h3>
                <p style="white-space:pre-line">${item.text.substring(0,100)}${item.text.length>100?'...':''}</p>
                ${item.link ? `<a href="${item.link}" target="_blank" class="btn btn-gold" style="margin-top:12px;display:inline-block;padding:10px 20px;font-size:14px">⬇️ دانلود فایل</a>` : ''}
                ${isAdmin ? `<br><button class="btn btn-red" style="margin-top:12px;padding:8px 16px;font-size:14px" onclick="delPost('${item.id}')">حذف پیام</button>` : ''}
            </div>
        `).join('');
}

function fillCatSelect(){
    const sel = document.getElementById('msg-cat');
    sel.innerHTML = DB.categories.map(c=>`<option value="${c.id}">${c.name}</option>`).join('');
}

// مدیریت پیام‌ها
function saveMsg(){
    const catId = document.getElementById('msg-cat').value;
    const title = document.getElementById('msg-title').value.trim();
    const text = document.getElementById('msg-body').value.trim();
    const link = document.getElementById('msg-link').value.trim();
    if(!title || !text) return alert('⚠️ عنوان و متن الزامی است!');
    DB.posts.push({
        id:'post_'+Date.now(),
        catId,title,text,link,
        date:new Date().toLocaleDateString('fa-IR')
    });
    document.getElementById('msg-title').value='';
    document.getElementById('msg-body').value='';
    document.getElementById('msg-link').value='';
    renderItems();
    renderAllMsgs();
    updateExport();
    alert('✅ پیام با موفقیت منتشر شد!');
}

function delPost(id){
    if(!confirm('حذف شود؟')) return;
    DB.posts = DB.posts.filter(p=>p.id!==id);
    renderItems();
    renderAllMsgs();
    updateExport();
}

function renderAllMsgs(){
    const cont = document.getElementById('msgs-list');
    cont.innerHTML = DB.posts.length===0 ? '<p style="color:var(--text-gold);text-align:center;padding:30px">هنوز پیامی وجود ندارد</p>' :
        DB.posts.map(item=>{
            const cat = DB.categories.find(c=>c.id===item.catId);
            return `
                <div class="msg-card">
                    <h4>${item.title} <span style="color:var(--gold-main);font-size:13px">(${cat?cat.name:'نامشخص'})</span></h4>
                    <p style="color:#4A3E00;white-space:pre-line;line-height:1.8">${item.text}</p>
                    ${item.link ? `<a href="${item.link}" target="_blank" style="color:var(--gold-dark);font-weight:700">🔗 لینک دانلود</a>` : ''}
                    <time>تاریخ انتشار: ${item.date}</time>
                </div>
            `;
        }).join('');
}

// ذخیره و بازیابی داده‌ها
function updateExport(){
    document.getElementById('data-code').value = JSON.stringify(DB,null,2);
}

function copyData(){
    navigator.clipboard.writeText(document.getElementById('data-code').value)
        .then(()=>alert('✅ کپی شد!\nحالا برو فایل index.html را باز کن → همه را پاک کن → این کد را بچسبون → ذخیره کن'))
        .catch(()=>alert('❌ کپی خودکار انجام نشد — دستی کپی کن'));
}

function loadData(){
    const input = prompt('کد داده‌ها را اینجا بچسبان:');
    if(!input) return;
    try{
        DB = JSON.parse(input);
        renderCats();
        renderAllMsgs();
        renderManageCats();
        fillCatSelect();
        updateExport();
        alert('✅ با موفقیت بارگذاری شد!');
    }catch{
        alert('❌ کد نامعتبر است!');
    }
}

function exitAdmin(){
    isAdmin=false;
    closeModal('admin-modal');
    document.getElementById('pass-input').value='';
    document.getElementById('err-msg').style.display='none';
}

// شروع
document.addEventListener('DOMContentLoaded',()=>{
    makeStars();
    // داده‌های پیش‌فرض
    if(DB.categories.length===0){
        DB.categories = [
            {id:'c1',name:'بازی‌های اکشن و ماجراجویی'},
            {id:'c2',name:'بازی‌های مسابقه‌ای و ورزشی'},
            {id:'c3',name:'فایل‌ها، بکاپ و منابع'}
        ];
        DB.posts = [
            {id:'p1',catId:'c1',title:'خوش آمدید به VORTEXPLAY',text:'این اولین پیام شماست!\n\nاز پنل مدیریت می‌توانید:\n✅ دسته‌بندی جدید بسازید\n✅ پیام و توضیحات اضافه کنید\n✅ لینک دانلود قرار دهید\n✅ همه چیز را ویرایش یا حذف کنید\n\nموفق باشید!',link:'',date:'۱۴۰۵/۰۷/۰۵'}
        ];
        updateExport();
    }
});
</script>
</body>
</html>
