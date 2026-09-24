<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VORTEXPLAY — قلمرو سلطنتی گیمینگ</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700;900&family=Vazirmatn:wght@300;500;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #f39c12;
            --gold-glow: #f1c40f;
            --gold-gradient: linear-gradient(135deg, #ffe066 0%, #f39c12 50%, #9a6a00 100%);
            --bg-dark: #07020d;
            --card-bg: rgba(20, 9, 36, 0.75);
            --border-gold: rgba(243, 156, 18, 0.4);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Vazirmatn', sans-serif; }

        body {
            background-color: var(--bg-dark);
            color: #f1f1f1;
            min-height: 100vh;
            overflow-x: hidden;
            padding-bottom: 100px;
            background-image: 
                radial-gradient(circle at 50% 0%, rgba(142, 68, 173, 0.25) 0%, transparent 70%),
                radial-gradient(circle at 80% 50%, rgba(243, 156, 18, 0.1) 0%, transparent 50%);
            background-attachment: fixed;
        }

        /* ذرات شناور طلایی */
        #particles {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: var(--gold-glow);
            border-radius: 50%;
            box-shadow: 0 0 10px var(--gold-glow);
            animation: flyUp linear infinite;
        }

        @keyframes flyUp {
            0% { transform: translateY(100vh) scale(0); opacity: 0; }
            50% { opacity: 0.9; }
            100% { transform: translateY(-10vh) scale(1.2); opacity: 0; }
        }

        /* هدر لوکس */
        header {
            text-align: center;
            padding: 50px 20px 20px;
            position: relative;
            z-index: 1;
        }

        .crown {
            font-size: 3.8rem;
            animation: floatCrown 3.5s ease-in-out infinite;
            display: inline-block;
            filter: drop-shadow(0 0 20px var(--gold-glow));
        }

        @keyframes floatCrown {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-12px) rotate(3deg); }
        }

        .logo-box {
            width: 130px; height: 130px;
            margin: 15px auto;
            position: relative;
            border-radius: 50%;
            padding: 6px;
            background: var(--gold-gradient);
            box-shadow: 0 0 30px rgba(243, 156, 18, 0.4);
        }

        .logo-box img {
            width: 100%; height: 100%;
            border-radius: 50%;
            object-fit: cover;
            background: #110522;
        }

        h1 {
            font-family: 'Cinzel', serif;
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 3rem;
            letter-spacing: 2px;
            text-shadow: 0 0 25px rgba(243, 156, 18, 0.3);
            margin-top: 10px;
        }

        .subtitle {
            color: #d1c4e9;
            font-size: 1.1rem;
            margin-top: 5px;
        }

        /* کاور پوستر */
        .cover-container {
            max-width: 950px;
            margin: 25px auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }

        .cover-card {
            border-radius: 20px;
            padding: 4px;
            background: var(--gold-gradient);
            box-shadow: 0 10px 40px rgba(0,0,0,0.8), 0 0 30px rgba(243, 156, 18, 0.2);
        }

        .cover-img {
            width: 100%;
            max-height: 400px;
            object-fit: cover;
            border-radius: 17px;
            display: block;
        }

        /* بدنه و کارت‌ها */
        .main-container {
            max-width: 1000px;
            margin: 40px auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }

        .section-header {
            color: var(--gold);
            font-size: 1.5rem;
            font-weight: 800;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 12px;
            border-bottom: 2px solid var(--border-gold);
            padding-bottom: 10px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-gold);
            border-radius: 16px;
            padding: 18px;
            backdrop-filter: blur(12px);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .card:hover {
            transform: translateY(-8px) scale(1.02);
            box-shadow: 0 15px 35px rgba(243, 156, 18, 0.3);
            border-color: var(--gold);
        }

        .card img {
            width: 100%; height: 170px;
            object-fit: cover;
            border-radius: 12px;
            margin-bottom: 12px;
        }

        .badge-price {
            background: var(--gold-gradient);
            color: #000;
            font-weight: 800;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            display: inline-block;
            margin-bottom: 10px;
        }

        .btn-gold {
            display: block;
            width: 100%;
            padding: 12px;
            background: var(--gold-gradient);
            border: none;
            color: #000;
            font-weight: 800;
            border-radius: 10px;
            cursor: pointer;
            text-align: center;
            text-decoration: none;
            transition: all 0.3s;
            margin-top: 12px;
        }

        .btn-gold:hover {
            filter: brightness(1.2);
            box-shadow: 0 0 15px var(--gold-glow);
        }

        /* بخش پیام‌ها */
        .box-panel {
            background: var(--card-bg);
            border: 1px solid var(--border-gold);
            padding: 25px;
            border-radius: 16px;
            margin-top: 40px;
            backdrop-filter: blur(10px);
        }

        .form-input {
            width: 100%;
            padding: 12px 15px;
            background: rgba(5, 1, 13, 0.7);
            border: 1px solid var(--border-gold);
            color: #fff;
            border-radius: 8px;
            margin-bottom: 15px;
            outline: none;
        }

        .form-input:focus {
            border-color: var(--gold-glow);
            box-shadow: 0 0 10px rgba(243, 156, 18, 0.3);
        }

        /* نوار مدیریت پایین */
        .bottom-bar {
            position: fixed;
            bottom: 0; left: 0; right: 0;
            background: rgba(7, 2, 13, 0.95);
            border-top: 1px solid var(--border-gold);
            padding: 15px 25px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 99;
            backdrop-filter: blur(15px);
        }

        /* مدال پنل مدیریت */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(8px);
            z-index: 1000;
            overflow-y: auto;
            padding: 20px;
        }

        .modal-body {
            background: #110522;
            border: 2px solid var(--gold);
            border-radius: 20px;
            max-width: 650px;
            margin: 40px auto;
            padding: 30px;
            position: relative;
            box-shadow: 0 0 50px rgba(243, 156, 18, 0.3);
        }

        .close-icon {
            position: absolute;
            left: 20px; top: 20px;
            color: var(--gold);
            font-size: 1.8rem;
            cursor: pointer;
        }

        .auth-status {
            padding: 10px;
            border-radius: 8px;
            margin-top: 12px;
            text-align: center;
            font-weight: bold;
            display: none;
        }

        .auth-status.error {
            background: rgba(192, 57, 43, 0.3);
            border: 1px solid #c0392b;
            color: #e74c3c;
        }

        .auth-status.success {
            background: rgba(39, 174, 96, 0.3);
            border: 1px solid #27ae60;
            color: #2ecc71;
        }
    </style>
</head>
<body>

    <div id="particles"></div>

    <header>
        <div class="crown">👑</div>
        <div class="logo-box">
            <img id="siteLogo" src="https://via.placeholder.com/150/f39c12/000000?text=VORTEX" alt="لوگو">
        </div>
        <h1 id="siteTitle">VORTEXPLAY</h1>
        <div class="subtitle" id="siteSubtitle">پادشاهی نهایی گیمرها ✨</div>
    </header>

    <div class="cover-container">
        <div class="cover-card">
            <img id="siteCover" class="cover-img" src="https://via.placeholder.com/900x400/110522/f39c12?text=VORTEXPLAY+ROYAL+GAMING" alt="کاور اصلی">
        </div>
    </div>

    <div class="main-container">
        <div class="section-header">🛍️ محصولات ویژه‌ی سلطنتی</div>
        <div class="products-grid" id="productsGrid"></div>

        <div class="box-panel">
            <div class="section-header" style="border:none; margin-bottom:15px;">📬 فرستادن نامه به مدیر پادشاهی</div>
            <input type="text" id="msgName" class="form-input" placeholder="نام شما (اختیاری)">
            <textarea id="msgContent" class="form-input" rows="3" placeholder="پیام خود را بنویسید..."></textarea>
            <button class="btn-gold" onclick="sendMessage()">ارسال پیام ✨</button>
        </div>
    </div>

    <!-- نوار ثابت مدیریت پایین صفحه -->
    <div class="bottom-bar">
        <span style="color: var(--gold); font-weight: bold;">👑 VORTEXPLAY Control Center</span>
        <button class="btn-gold" style="width: auto; padding: 8px 20px;" onclick="openAdmin()">⚙️ ورود به پنل مدیر</button>
    </div>

    <!-- پنجره مدیریت -->
    <div id="adminModal" class="modal">
        <div class="modal-body">
            <span class="close-icon" onclick="closeAdmin()">&times;</span>
            <h2 style="color: var(--gold); margin-bottom: 20px;">⚙️ مدیریت VORTEXPLAY</h2>

            <div id="loginSection">
                <p style="margin-bottom: 10px;">رمز عبور ۳۲ رقمی مدیر را وارد کنید:</p>
                <input type="password" id="adminPass" class="form-input" placeholder="رمز ۳۲ رقمی...">
                <button class="btn-gold" onclick="loginAdmin()">بررسی رمز و ورود</button>
                <div id="authStatus" class="auth-status"></div>
            </div>

            <div id="controlSection" style="display: none;">
                <!-- ۱. ویرایش عناوین -->
                <div style="margin-bottom: 25px;">
                    <h3 style="color: var(--gold-glow); margin-bottom: 10px;">📝 تغییر عنوان و زیرعنوان</h3>
                    <input type="text" id="editTitle" class="form-input" placeholder="عنوان جدید سایت">
                    <input type="text" id="editSubtitle" class="form-input" placeholder="زیرعنوان جدید">
                    <button class="btn-gold" style="background: #27ae60; color:#fff;" onclick="applyTextChanges()">✅ تأیید و اعمال تغییرات</button>
                </div>

                <hr style="border-color: var(--border-gold); margin: 20px 0;">

                <!-- ۲. افزودن محصول -->
                <div style="margin-bottom: 25px;">
                    <h3 style="color: var(--gold-glow); margin-bottom: 10px;">🛍️ افزودن محصول جدید</h3>
                    <input type="text" id="prodTitle" class="form-input" placeholder="نام محصول">
                    <input type="text" id="prodDesc" class="form-input" placeholder="توضیحات کوتاه">
                    <input type="text" id="prodPrice" class="form-input" placeholder="قیمت (مثلاً: رایگان یا ۵۰,۰۰۰ تومان)">
                    <input type="text" id="prodImg" class="form-input" placeholder="لینک عکس محصول">
                    <input type="text" id="prodLink" class="form-input" placeholder="لینک دریافت/دانلود">
                    <button class="btn-gold" style="background: #27ae60; color:#fff;" onclick="addNewProduct()">✅ تأیید و افزودن محصول</button>
                </div>

                <hr style="border-color: var(--border-gold); margin: 20px 0;">

                <!-- ۳. صندوق پیام‌ها -->
                <div>
                    <h3 style="color: var(--gold-glow); margin-bottom: 10px;">📬 صندوق پیام‌های دریافت شده</h3>
                    <div id="messagesContainer" style="max-height: 200px; overflow-y: auto;"></div>
                </div>

                <button class="btn-gold" style="background: #c0392b; color:#fff; margin-top:25px;" onclick="logoutAdmin()">خروج از حساب مدیر</button>
            </div>
        </div>
    </div>

    <script>
        // 🔑 رمز دقیقاً ۳۲ رقمی مدیر
        const SECRET_KEY_32 = "12345678901234567890123456789032";

        let defaultData = {
            title: "VORTEXPLAY",
            subtitle: "پادشاهی نهایی گیمرها ✨",
            logo: "https://via.placeholder.com/150/f39c12/000000?text=VORTEX",
            cover: "https://via.placeholder.com/900x400/110522/f39c12?text=VORTEXPLAY+ROYAL+GAMING",
            products: [
                {
                    title: "اکانت ویژه گیمینگ VORTEX",
                    desc: "دسترسی نامحدود به تمامی خدمات سلطنتی",
                    price: "رایگان",
                    img: "https://via.placeholder.com/300/110522/f39c12?text=VIP+ACCOUNT",
                    link: "#"
                }
            ],
            messages: []
        };

        function getStore() {
            let data = localStorage.getItem('vortex_data');
            return data ? JSON.parse(data) : defaultData;
        }

        function saveStore(data) {
            localStorage.setItem('vortex_data', JSON.stringify(data));
            renderSite();
        }

        function renderSite() {
            let data = getStore();
            document.getElementById('siteTitle').innerText = data.title;
            document.getElementById('siteSubtitle').innerText = data.subtitle;
            document.getElementById('siteLogo').src = data.logo;
            document.getElementById('siteCover').src = data.cover;

            let grid = document.getElementById('productsGrid');
            grid.innerHTML = '';
            data.products.forEach(p => {
                grid.innerHTML += `
                    <div class="card">
                        <img src="${p.img}" alt="${p.title}">
                        <div class="badge-price">${p.price}</div>
                        <h3 style="margin-bottom:5px;">${p.title}</h3>
                        <p style="font-size:0.85rem; color:#aaa;">${p.desc}</p>
                        <a href="${p.link}" target="_blank" class="btn-gold">⬇️ دریافت مستقیم</a>
                    </div>
                `;
            });
        }

        function sendMessage() {
            let name = document.getElementById('msgName').value || 'ناشناس';
            let content = document.getElementById('msgContent').value;
            if(!content) return alert('لطفا متن پیام را بنویسید!');

            let data = getStore();
            data.messages.push({ name, content, date: new Date().toLocaleTimeString('fa-IR') });
            saveStore(data);
            alert('پیام شما با موفقیت برای مدیر فرستاده شد ✨');
            document.getElementById('msgContent').value = '';
        }

        function openAdmin() { 
            document.getElementById('adminModal').style.display = 'block'; 
            document.getElementById('authStatus').style.display = 'none';
        }

        function closeAdmin() { 
            document.getElementById('adminModal').style.display = 'none'; 
        }

        // بررسی رمز عبور (اشتباه/درست)
        function loginAdmin() {
            let passInput = document.getElementById('adminPass').value;
            let statusDiv = document.getElementById('authStatus');

            statusDiv.style.display = 'block';

            if(passInput === SECRET_KEY_32) {
                statusDiv.className = 'auth-status success';
                statusDiv.innerText = '✅ رمز عبور درست است! در حال ورود...';
                
                setTimeout(() => {
                    document.getElementById('loginSection').style.display = 'none';
                    document.getElementById('controlSection').style.display = 'block';
                    loadMessages();
                }, 1000);
            } else {
                statusDiv.className = 'auth-status error';
                statusDiv.innerText = '❌ رمز عبور اشتباه است! دوباره تلاش کنید.';
            }
        }

        function logoutAdmin() {
            document.getElementById('loginSection').style.display = 'block';
            document.getElementById('controlSection').style.display = 'none';
            document.getElementById('adminPass').value = '';
            document.getElementById('authStatus').style.display = 'none';
            closeAdmin();
        }

        function applyTextChanges() {
            let t = document.getElementById('editTitle').value;
            let st = document.getElementById('editSubtitle').value;
            let data = getStore();
            if(t) data.title = t;
            if(st) data.subtitle = st;
            saveStore(data);
            alert('تغییرات با موفقیت روی سایت اعمال شد!');
        }

        function addNewProduct() {
            let p = {
                title: document.getElementById('prodTitle').value,
                desc: document.getElementById('prodDesc').value,
                price: document.getElementById('prodPrice').value || 'رایگان',
                img: document.getElementById('prodImg').value || 'https://via.placeholder.com/300',
                link: document.getElementById('prodLink').value || '#'
            };
            if(!p.title) return alert('نام محصول الزامی است!');
            let data = getStore();
            data.products.push(p);
            saveStore(data);
            alert('محصول جدید اضافه شد!');
        }

        function loadMessages() {
            let data = getStore();
            let container = document.getElementById('messagesContainer');
            container.innerHTML = '';
            data.messages.forEach(m => {
                container.innerHTML += `
                    <div style="background:rgba(255,255,255,0.05); padding:10px; border-radius:8px; margin-bottom:8px;">
                        <strong>${m.name}</strong> (${m.date}):
                        <p style="font-size:0.9rem; color:#ddd;">${m.content}</p>
                    </div>
                `;
            });
            if(data.messages.length === 0) container.innerHTML = '<p style="color:#888;">هیچ پیامی وجود ندارد.</p>';
        }

        // انیمیشن ذرات
        (function createParticles() {
            const container = document.getElementById('particles');
            for(let i=0; i<30; i++) {
                let p = document.createElement('div');
                p.className = 'particle';
                let size = Math.random() * 4 + 2;
                p.style.width = size + 'px';
                p.style.height = size + 'px';
                p.style.left = Math.random() * 100 + 'vw';
                p.style.animationDuration = (Math.random() * 8 + 4) + 's';
                p.style.animationDelay = Math.random() * 5 + 's';
                container.appendChild(p);
            }
        })();

        renderSite();
    </script>
</body>
</html>
