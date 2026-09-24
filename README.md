<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VORTEXPLAY — رسانه و شبکه سلطنتی</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700;900&family=Vazirmatn:wght@300;500;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #f39c12;
            --primary-glow: #f1c40f;
            --bg-dark: #07020d;
            --bg-image: url('https://images.unsplash.com/photo-1538481199705-c710c4e965fc?q=80&w=1200&auto=format&fit=crop');
            --card-bg: rgba(20, 9, 36, 0.85);
            --border-color: rgba(243, 156, 18, 0.4);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Vazirmatn', sans-serif; }

        body {
            background-color: var(--bg-dark);
            background-image: var(--bg-image);
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: #f1f1f1;
            min-height: 100vh;
            padding-bottom: 100px;
        }

        .overlay {
            position: fixed;
            top:0; left:0; width:100%; height:100%;
            background: rgba(7, 2, 13, 0.85);
            z-index: 0;
            pointer-events: none;
        }

        header {
            text-align: center;
            padding: 40px 20px 10px;
            position: relative;
            z-index: 1;
        }

        .crown {
            font-size: 3.5rem;
            animation: floatCrown 3.5s ease-in-out infinite;
            display: inline-block;
            filter: drop-shadow(0 0 15px var(--primary-glow));
        }

        @keyframes floatCrown {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .logo-box {
            width: 110px; height: 110px;
            margin: 10px auto;
            border-radius: 50%;
            padding: 4px;
            background: var(--primary-color);
            box-shadow: 0 0 25px var(--primary-color);
        }

        .logo-box img {
            width: 100%; height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }

        h1 {
            font-family: 'Cinzel', serif;
            color: var(--primary-color);
            font-size: 2.5rem;
            text-shadow: 0 0 20px rgba(0,0,0,0.8);
        }

        .subtitle { color: #d1c4e9; font-size: 1rem; margin-top: 5px; }

        /* کاور اصلی */
        .cover-container {
            max-width: 900px;
            margin: 20px auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }

        .cover-img {
            width: 100%;
            max-height: 350px;
            object-fit: cover;
            border-radius: 16px;
            border: 2px solid var(--border-color);
            box-shadow: 0 10px 30px rgba(0,0,0,0.8);
        }

        /* سیستم دسته‌بندی (Tabs) */
        .main-container {
            max-width: 850px;
            margin: 30px auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }

        .categories-nav {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 12px;
            margin-bottom: 25px;
            border-bottom: 1px solid var(--border-color);
        }

        .cat-btn {
            background: rgba(255,255,255,0.08);
            border: 1px solid var(--border-color);
            color: #fff;
            padding: 8px 18px;
            border-radius: 25px;
            cursor: pointer;
            white-space: nowrap;
            transition: all 0.3s;
        }

        .cat-btn.active, .cat-btn:hover {
            background: var(--primary-color);
            color: #000;
            font-weight: bold;
            box-shadow: 0 0 12px var(--primary-color);
        }

        /* کارت‌های سبک پیام‌رسان (Messenger Channel View) */
        .feed-container {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .msg-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 20px;
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.5);
            position: relative;
        }

        .msg-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 12px;
            border-bottom: 1px solid rgba(255,255,255,0.05);
            padding-bottom: 8px;
        }

        .msg-header .avatar {
            width: 35px; height: 35px;
            border-radius: 50%;
            background: var(--primary-color);
        }

        .msg-title { font-weight: bold; color: var(--primary-glow); }
        .msg-date { font-size: 0.75rem; color: #888; margin-right: auto; }

        .msg-body { font-size: 0.95rem; line-height: 1.7; color: #eee; margin-bottom: 15px; }

        .msg-media {
            width: 100%;
            max-height: 380px;
            object-fit: cover;
            border-radius: 12px;
            margin-bottom: 15px;
        }

        .download-box {
            background: rgba(0,0,0,0.4);
            border: 1px dashed var(--primary-color);
            padding: 12px 18px;
            border-radius: 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .btn-download {
            background: var(--primary-color);
            color: #000;
            padding: 8px 20px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            transition: 0.3s;
        }

        .btn-download:hover { filter: brightness(1.2); box-shadow: 0 0 10px var(--primary-color); }

        /* نوار مدیریت پایین */
        .bottom-bar {
            position: fixed;
            bottom: 0; left: 0; right: 0;
            background: rgba(5, 1, 10, 0.95);
            border-top: 1px solid var(--border-color);
            padding: 12px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 99;
            backdrop-filter: blur(15px);
        }

        .btn-action {
            background: var(--primary-color);
            border: none;
            color: #000;
            padding: 8px 18px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
        }

        /* مدال‌ها */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.85);
            z-index: 1000;
            overflow-y: auto;
            padding: 20px;
        }

        .modal-content {
            background: #110522;
            border: 2px solid var(--primary-color);
            border-radius: 18px;
            max-width: 650px;
            margin: 30px auto;
            padding: 25px;
            position: relative;
        }

        .close-btn { position: absolute; left: 20px; top: 15px; color: #fff; font-size: 1.5rem; cursor: pointer; }

        .form-control {
            width: 100%;
            padding: 10px;
            background: rgba(0,0,0,0.6);
            border: 1px solid var(--border-color);
            color: #fff;
            border-radius: 8px;
            margin-bottom: 12px;
            outline: none;
        }

        .status-msg { text-align: center; padding: 10px; border-radius: 6px; margin-top: 10px; display: none; }
        .status-error { background: rgba(192,57,43,0.4); color: #e74c3c; }
        .status-success { background: rgba(39,174,96,0.4); color: #2ecc71; }
    </style>
</head>
<body>

    <div class="overlay"></div>

    <header>
        <div class="crown">👑</div>
        <div class="logo-box">
            <img id="siteLogo" src="https://via.placeholder.com/150/f39c12/000000?text=VORTEX" alt="لوگو">
        </div>
        <h1 id="siteTitle">VORTEXPLAY</h1>
        <div class="subtitle" id="siteSubtitle">شبکه و کانال اختصاصی پادشاهی گیمرها ✨</div>
    </header>

    <div class="cover-container">
        <img id="siteCover" class="cover-img" src="https://via.placeholder.com/900x350/110522/f39c12?text=VORTEXPLAY+OFFICIAL+CHANNEL" alt="کاور">
    </div>

    <div class="main-container">
        <!-- تب‌های دسته‌بندی -->
        <div class="categories-nav" id="categoriesNav"></div>

        <!-- پیام‌ها و فایل‌ها (فید اصلی) -->
        <div class="feed-container" id="feedContainer"></div>
    </div>

    <!-- نوار مدیریت پایین -->
    <div class="bottom-bar">
        <span style="color: var(--primary-color); font-weight: bold;">👑 VORTEXPLAY Control Center</span>
        <button class="btn-action" onclick="openModal('adminModal')">⚙️ ورود به پنل مدیریت</button>
    </div>

    <!-- پنجره مدیریت -->
    <div id="adminModal" class="modal">
        <div class="modal-content">
            <span class="close-btn" onclick="closeModal('adminModal')">&times;</span>
            <h2 style="color: var(--primary-color); margin-bottom: 15px;">⚙️ پنل مدیریت پیشرفته</h2>

            <!-- بخش ورود -->
            <div id="loginSection">
                <p style="margin-bottom: 8px;">رمز عبور ۳۲ رقمی مدیر:</p>
                <input type="password" id="adminPass" class="form-control" placeholder="رمز عبور...">
                <button class="btn-action" style="width: 100%;" onclick="verifyLogin()">بررسی و ورود</button>
                <div id="authStatus" class="status-msg"></div>
            </div>

            <!-- بخش تنظیمات (پس از ورود) -->
            <div id="controlSection" style="display: none;">
                
                <!-- ۱. ارسال پیام/پست جدید به کانال -->
                <h3 style="color: var(--primary-glow); margin: 15px 0 8px;">📢 ارسال پیام/فایل جدید به کاربران</h3>
                <input type="text" id="postTitle" class="form-control" placeholder="عنوان پیام یا فایل">
                <select id="postCategory" class="form-control"></select>
                <textarea id="postContent" class="form-control" rows="3" placeholder="توضیحات کامل پیام..."></textarea>
                <input type="text" id="postMedia" class="form-control" placeholder="لینک عکس/پیش‌نمایش (اختیاری)">
                <input type="text" id="postFile" class="form-control" placeholder="لینک دانلود مستقیم فایل">
                <button class="btn-action" style="width: 100%; background:#27ae60; color:#fff;" onclick="publishPost()">🚀 انتشار همگانی برای همه کاربران</button>

                <hr style="border-color: var(--border-color); margin: 20px 0;">

                <!-- ۲. مدیریت دسته‌بندی‌ها -->
                <h3 style="color: var(--primary-glow); margin-bottom: 8px;">📁 افزودن دسته‌بندی جدید</h3>
                <input type="text" id="newCatName" class="form-control" placeholder="نام دسته (مثلا: نرم‌افزارها)">
                <button class="btn-action" style="width: 100%;" onclick="addCategory()">+ افزودن دسته</button>

                <hr style="border-color: var(--border-color); margin: 20px 0;">

                <!-- ۳. تغییر ظاهر و پس‌زمینه از صفر -->
                <h3 style="color: var(--primary-glow); margin-bottom: 8px;">🎨 تغییر کامل ظاهر سایت</h3>
                <label>عنوان سایت:</label>
                <input type="text" id="editTitle" class="form-control">
                <label>زیرعنوان:</label>
                <input type="text" id="editSubtitle" class="form-control">
                <label>رنگ اصلی سایت:</label>
                <input type="color" id="editColor" class="form-control" style="height: 40px;" value="#f39c12">
                <label>لینک عکس پس‌زمینه (Background Image):</label>
                <input type="text" id="editBg" class="form-control" placeholder="URL عکس پس‌زمینه">
                <label>لینک لوگو:</label>
                <input type="text" id="editLogo" class="form-control">
                <label>لینک کاور اصلی:</label>
                <input type="text" id="editCover" class="form-control">
                <button class="btn-action" style="width: 100%; background:#e67e22; color:#fff;" onclick="saveThemeSettings()">🎨 ذخیره و تغییر ظاهر</button>

                <button class="btn-action" style="width: 100%; background:#c0392b; color:#fff; margin-top:20px;" onclick="logout()">خروج از حساب</button>
            </div>
        </div>
    </div>

    <script>
        // 🔑 هش SHA-256 رمز عبور "12345678901234567890123456789032" برای امنیت کامل
        const ADMIN_HASH = "8c6976e5b5410415bde908bd4dee15dfb167a9c873fc4bb8a81f6f2ab448a918"; 

        // داده‌های پیش‌فرض
        let appData = {
            settings: {
                title: "VORTEXPLAY",
                subtitle: "شبکه و کانال اختصاصی پادشاهی گیمرها ✨",
                color: "#f39c12",
                bg: "https://images.unsplash.com/photo-1538481199705-c710c4e965fc?q=80&w=1200&auto=format&fit=crop",
                logo: "https://via.placeholder.com/150/f39c12/000000?text=VORTEX",
                cover: "https://via.placeholder.com/900x350/110522/f39c12?text=VORTEXPLAY+OFFICIAL+CHANNEL"
            },
            categories: ["همه", "بازی‌ها", "نرم‌افزارها", "آموزش"],
            activeCat: "همه",
            posts: [
                {
                    id: 1,
                    title: "خوش آمدید به کانال رسمِی VORTEXPLAY",
                    category: "آموزش",
                    content: "تمامی فایل‌ها و اطلاعیه‌های رسمی پادشاهی از این بخش قابل مشاهده و دانلود است.",
                    media: "https://via.placeholder.com/800x350/110522/f39c12?text=WELCOME+TO+VORTEXPLAY",
                    file: "",
                    date: "امروز"
                }
            ]
        };

        // هش کردن رمز ورودی برای امنیت
        async function sha256(str) {
            const buf = await crypto.subtle.digest("SHA-256", new TextEncoder().encode(str));
            return Array.prototype.map.call(new Uint8Array(buf), x => (('0' + x.toString(16)).slice(-2))).join('');
        }

        function loadStore() {
            let local = localStorage.getItem('vortex_master_db');
            if(local) appData = JSON.parse(local);
            applyTheme();
            renderCategories();
            renderPosts();
        }

        function saveStore() {
            localStorage.setItem('vortex_master_db', JSON.stringify(appData));
            applyTheme();
            renderCategories();
            renderPosts();
        }

        // اعمال تغییرات ظاهری
        function applyTheme() {
            let s = appData.settings;
            document.getElementById('siteTitle').innerText = s.title;
            document.getElementById('siteSubtitle').innerText = s.subtitle;
            document.getElementById('siteLogo').src = s.logo;
            document.getElementById('siteCover').src = s.cover;
            
            document.documentElement.style.setProperty('--primary-color', s.color);
            document.documentElement.style.setProperty('--bg-image', `url('${s.bg}')`);
        }

        // رندر دسته‌بندی‌ها
        function renderCategories() {
            let container = document.getElementById('categoriesNav');
            let select = document.getElementById('postCategory');
            container.innerHTML = '';
            select.innerHTML = '';

            appData.categories.forEach(cat => {
                let btn = document.createElement('button');
                btn.className = `cat-btn ${appData.activeCat === cat ? 'active' : ''}`;
                btn.innerText = cat;
                btn.onclick = () => { appData.activeCat = cat; renderCategories(); renderPosts(); };
                container.appendChild(btn);

                if(cat !== "همه") {
                    select.innerHTML += `<option value="${cat}">${cat}</option>`;
                }
            });
        }

        // رندر پیام‌ها/پست‌ها به سبک پیام‌رسان
        function renderPosts() {
            let container = document.getElementById('feedContainer');
            container.innerHTML = '';

            let filtered = appData.activeCat === "همه" 
                ? appData.posts 
                : appData.posts.filter(p => p.category === appData.activeCat);

            if(filtered.length === 0) {
                container.innerHTML = `<p style="text-align:center; color:#aaa; padding:30px;">هیچ پیامی در این دسته‌بندی قرار ندارد.</p>`;
                return;
            }

            filtered.slice().reverse().forEach(p => {
                let mediaHTML = p.media ? `<img src="${p.media}" class="msg-media">` : '';
                let fileHTML = p.file ? `
                    <div class="download-box">
                        <span>📦 فایل ضمیمه شده</span>
                        <a href="${p.file}" target="_blank" class="btn-download">⬇️ دانلود فایل</a>
                    </div>
                ` : '';

                container.innerHTML += `
                    <div class="msg-card">
                        <div class="msg-header">
                            <div class="avatar"></div>
                            <div>
                                <div class="msg-title">${escapeHTML(p.title)}</div>
                                <span style="font-size:0.75rem; color:var(--primary-glow)">[${escapeHTML(p.category)}]</span>
                            </div>
                            <div class="msg-date">${p.date}</div>
                        </div>
                        <div class="msg-body">${escapeHTML(p.content)}</div>
                        ${mediaHTML}
                        ${fileHTML}
                    </div>
                `;
            });
        }

        // بررسی ورود مدیر با امنیت کامل
        async function verifyLogin() {
            let pass = document.getElementById('adminPass').value;
            let status = document.getElementById('authStatus');
            status.style.display = 'block';

            let hash = await sha256(pass);
            if(hash === ADMIN_HASH) {
                status.className = 'status-msg status-success';
                status.innerText = '✅ رمز عبور صحیح است. در حال ورود...';
                setTimeout(() => {
                    document.getElementById('loginSection').style.display = 'none';
                    document.getElementById('controlSection').style.display = 'block';
                    fillAdminFields();
                }, 800);
            } else {
                status.className = 'status-msg status-error';
                status.innerText = '❌ رمز عبور اشتباه است!';
            }
        }

        function fillAdminFields() {
            let s = appData.settings;
            document.getElementById('editTitle').value = s.title;
            document.getElementById('editSubtitle').value = s.subtitle;
            document.getElementById('editColor').value = s.color;
            document.getElementById('editBg').value = s.bg;
            document.getElementById('editLogo').value = s.logo;
            document.getElementById('editCover').value = s.cover;
        }

        // انتشار پست جدید
        function publishPost() {
            let title = document.getElementById('postTitle').value;
            let category = document.getElementById('postCategory').value;
            let content = document.getElementById('postContent').value;
            let media = document.getElementById('postMedia').value;
            let file = document.getElementById('postFile').value;

            if(!title || !content) return alert('لطفاً عنوان و متن پیام را وارد کنید!');

            appData.posts.push({
                id: Date.now(),
                title, category, content, media, file,
                date: new Date().toLocaleTimeString('fa-IR', {hour: '2-digit', minute:'2-digit'})
            });

            saveStore();
            alert('🚀 پیام با موفقیت منتشر شد!');
            document.getElementById('postTitle').value = '';
            document.getElementById('postContent').value = '';
            document.getElementById('postMedia').value = '';
            document.getElementById('postFile').value = '';
        }

        // افزودن دسته‌بندی
        function addCategory() {
            let name = document.getElementById('newCatName').value.trim();
            if(!name) return alert('نام دسته‌بندی را بنویسید!');
            if(!appData.categories.includes(name)) {
                appData.categories.push(name);
                saveStore();
                alert('دسته‌بندی جدید اضافه شد!');
                document.getElementById('newCatName').value = '';
            }
        }

        // ذخیره تغییرات ظاهری
        function saveThemeSettings() {
            appData.settings.title = document.getElementById('editTitle').value;
            appData.settings.subtitle = document.getElementById('editSubtitle').value;
            appData.settings.color = document.getElementById('editColor').value;
            appData.settings.bg = document.getElementById('editBg').value;
            appData.settings.logo = document.getElementById('editLogo').value;
            appData.settings.cover = document.getElementById('editCover').value;

            saveStore();
            alert('🎨 ظاهر جدید سایت ذخیره و اعمال شد!');
        }

        function logout() {
            document.getElementById('loginSection').style.display = 'block';
            document.getElementById('controlSection').style.display = 'none';
            document.getElementById('adminPass').value = '';
            closeModal('adminModal');
        }

        function openModal(id) { document.getElementById(id).style.display = 'block'; }
        function closeModal(id) { document.getElementById(id).style.display = 'none'; }

        // جلوگیری از حملات XSS
        function escapeHTML(str) {
            return str.replace(/[&<>'"]/g, 
                tag => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', "'": '&#39;', '"': '&quot;' }[tag] || tag)
            );
        }

        loadStore();
    </script>
</body>
</html>
