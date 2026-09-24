<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>فروشگاه VORTEXPLAY</title>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;500;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #f39c12;
            --bg-dark: #0a0512;
            --card-bg: rgba(22, 11, 36, 0.9);
            --border-color: rgba(243, 156, 18, 0.4);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Vazirmatn', sans-serif; }

        body {
            background-color: var(--bg-dark);
            color: #fff;
            min-height: 100vh;
            padding-bottom: 90px;
        }

        header {
            text-align: center;
            padding: 30px 20px 10px;
        }

        .logo-box {
            width: 100px; height: 100px;
            margin: 0 auto 10px;
            border-radius: 50%;
            border: 3px solid var(--primary-color);
            overflow: hidden;
            box-shadow: 0 0 20px var(--primary-color);
        }

        .logo-box img { width: 100%; height: 100%; object-fit: cover; }

        h1 { color: var(--primary-color); font-size: 2rem; margin-bottom: 5px; }

        .cover-container {
            max-width: 900px;
            margin: 15px auto;
            padding: 0 15px;
        }

        .cover-img {
            width: 100%;
            max-height: 280px;
            object-fit: cover;
            border-radius: 12px;
            border: 1px solid var(--border-color);
        }

        .main-container {
            max-width: 900px;
            margin: 20px auto;
            padding: 0 15px;
        }

        /* منوی دسته‌بندی */
        .cat-nav {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 10px;
            margin-bottom: 20px;
            border-bottom: 1px solid var(--border-color);
        }

        .cat-btn {
            background: rgba(255,255,255,0.05);
            border: 1px solid var(--border-color);
            color: #fff;
            padding: 8px 18px;
            border-radius: 20px;
            cursor: pointer;
            white-space: nowrap;
        }

        .cat-btn.active {
            background: var(--primary-color);
            color: #000;
            font-weight: bold;
        }

        /* شبکه محصولات فروشگاه */
        .shop-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .product-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 15px;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .product-card img {
            width: 100%;
            height: 160px;
            object-fit: cover;
            border-radius: 8px;
            margin-bottom: 10px;
        }

        .price-tag {
            color: var(--primary-color);
            font-weight: bold;
            font-size: 1.1rem;
            margin: 8px 0;
        }

        .btn-buy {
            background: var(--primary-color);
            color: #000;
            text-decoration: none;
            padding: 10px;
            border-radius: 8px;
            font-weight: bold;
            display: block;
            margin-top: 10px;
        }

        /* نوار مدیریت پایین */
        .bottom-bar {
            position: fixed;
            bottom: 0; left: 0; right: 0;
            background: #05020a;
            border-top: 1px solid var(--border-color);
            padding: 12px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .btn-admin {
            background: var(--primary-color);
            border: none;
            padding: 8px 16px;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
        }

        /* مدال مدیریت */
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
            background: #120824;
            border: 2px solid var(--primary-color);
            border-radius: 12px;
            max-width: 500px;
            margin: 40px auto;
            padding: 20px;
            position: relative;
        }

        .close-btn { position: absolute; left: 15px; top: 15px; cursor: pointer; font-size: 1.5rem; }

        .form-control {
            width: 100%;
            padding: 10px;
            background: rgba(0,0,0,0.5);
            border: 1px solid var(--border-color);
            color: #fff;
            border-radius: 6px;
            margin-bottom: 10px;
            outline: none;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-box">
            <img id="siteLogo" src="https://via.placeholder.com/100/f39c12/000000?text=STORE" alt="لوگو">
        </div>
        <h1 id="siteTitle">فروشگاه VORTEXPLAY</h1>
        <p id="siteSubtitle" style="color: #aaa;">مرجع فروش محصولات و اکانت‌های گیمینگ</p>
    </header>

    <div class="cover-container">
        <img id="siteCover" class="cover-img" src="https://via.placeholder.com/900x280/120824/f39c12?text=VORTEXPLAY+STORE" alt="کاور">
    </div>

    <div class="main-container">
        <!-- منوی دسته‌بندی -->
        <div class="cat-nav" id="catNav"></div>

        <!-- کارت‌های محصولات -->
        <div class="shop-grid" id="shopGrid"></div>
    </div>

    <!-- نوار مدیریت -->
    <div class="bottom-bar">
        <span>🛒 فروشگاه فعال است</span>
        <button class="btn-admin" onclick="openAdmin()">⚙️ ورود به مدیریت</button>
    </div>

    <!-- پنجره مدیریت -->
    <div id="adminModal" class="modal">
        <div class="modal-content">
            <span class="close-btn" onclick="closeAdmin()">&times;</span>
            <h3 style="color: var(--primary-color); margin-bottom: 15px;">ورود به مدیریت فروشگاه</h3>

            <div id="loginForm">
                <input type="password" id="adminPass" class="form-control" placeholder="رمز عبور مدیر">
                <button class="btn-admin" style="width: 100%; margin-top: 5px;" onclick="checkPassword()">ورود</button>
                <p id="errorMsg" style="color: #ff4d4d; margin-top: 10px; display: none; text-align: center;">❌ رمز عبور اشتباه است!</p>
            </div>

            <div id="adminPanel" style="display: none;">
                <h4 style="color: var(--primary-color); margin-bottom: 10px;">➕ افزودن محصول جدید</h4>
                <input type="text" id="pTitle" class="form-control" placeholder="نام محصول">
                <select id="pCat" class="form-control"></select>
                <input type="text" id="pPrice" class="form-control" placeholder="قیمت (مثلا: ۵۰,۰۰۰ تومان)">
                <input type="text" id="pImg" class="form-control" placeholder="لینک عکس محصول">
                <input type="text" id="pLink" class="form-control" placeholder="لینک دانلود یا خرید">
                <button class="btn-admin" style="width: 100%; background: #27ae60; color:#fff;" onclick="addProduct()">افزودن محصول</button>

                <hr style="border-color: var(--border-color); margin: 15px 0;">

                <h4 style="color: var(--primary-color); margin-bottom: 10px;">📂 افزودن دسته‌بندی</h4>
                <input type="text" id="newCat" class="form-control" placeholder="نام دسته جدید">
                <button class="btn-admin" style="width: 100%;" onclick="addCategory()">افزودن دسته</button>

                <hr style="border-color: var(--border-color); margin: 15px 0;">

                <h4 style="color: var(--primary-color); margin-bottom: 10px;">🎨 تغییر ظاهر فروشگاه</h4>
                <input type="text" id="editTitle" class="form-control" placeholder="نام فروشگاه">
                <input type="text" id="editLogo" class="form-control" placeholder="لینک عکس لوگو">
                <input type="text" id="editCover" class="form-control" placeholder="لینک عکس کاور">
                <button class="btn-admin" style="width: 100%; background: #e67e22; color:#fff;" onclick="saveTheme()">ذخیره تغییرات ظاهر</button>
            </div>
        </div>
    </div>

    <script>
        // 🔑 رمز عبور جدید و ساده مدیریت
        const ADMIN_PASS = "12345678";

        let shopData = {
            settings: {
                title: "فروشگاه VORTEXPLAY",
                subtitle: "مرجع فروش محصولات و اکانت‌های گیمینگ",
                logo: "https://via.placeholder.com/100/f39c12/000000?text=STORE",
                cover: "https://via.placeholder.com/900x280/120824/f39c12?text=VORTEXPLAY+STORE"
            },
            categories: ["همه", "اکانت‌ها", "برنامه‌ها"],
            activeCat: "همه",
            products: [
                {
                    title: "اکانت ویژه VORTEX",
                    category: "اکانت‌ها",
                    price: "رایگان",
                    img: "https://via.placeholder.com/250/120824/f39c12?text=VIP+ACCOUNT",
                    link: "#"
                }
            ]
        };

        function loadData() {
            let saved = localStorage.getItem('vortex_shop_db');
            if(saved) shopData = JSON.parse(saved);
            renderStore();
        }

        function saveData() {
            localStorage.setItem('vortex_shop_db', JSON.stringify(shopData));
            renderStore();
        }

        function renderStore() {
            document.getElementById('siteTitle').innerText = shopData.settings.title;
            document.getElementById('siteSubtitle').innerText = shopData.settings.subtitle;
            document.getElementById('siteLogo').src = shopData.settings.logo;
            document.getElementById('siteCover').src = shopData.settings.cover;

            // رندر دسته‌ها
            let catNav = document.getElementById('catNav');
            let pCat = document.getElementById('pCat');
            catNav.innerHTML = '';
            pCat.innerHTML = '';

            shopData.categories.forEach(c => {
                let btn = document.createElement('button');
                btn.className = `cat-btn ${shopData.activeCat === c ? 'active' : ''}`;
                btn.innerText = c;
                btn.onclick = () => { shopData.activeCat = c; renderStore(); };
                catNav.appendChild(btn);

                if(c !== "همه") pCat.innerHTML += `<option value="${c}">${c}</option>`;
            });

            // رندر محصولات
            let grid = document.getElementById('shopGrid');
            grid.innerHTML = '';

            let filtered = shopData.activeCat === "همه" 
                ? shopData.products 
                : shopData.products.filter(p => p.category === shopData.activeCat);

            filtered.forEach(p => {
                grid.innerHTML += `
                    <div class="product-card">
                        <img src="${p.img}" alt="${p.title}">
                        <h3>${p.title}</h3>
                        <div class="price-tag">${p.price}</div>
                        <a href="${p.link}" target="_blank" class="btn-buy">🛒 دریافت / دانلود</a>
                    </div>
                `;
            });
        }

        function openAdmin() { document.getElementById('adminModal').style.display = 'block'; }
        function closeAdmin() { document.getElementById('adminModal').style.display = 'none'; }

        function checkPassword() {
            let input = document.getElementById('adminPass').value;
            if(input === ADMIN_PASS) {
                document.getElementById('loginForm').style.display = 'none';
                document.getElementById('adminPanel').style.display = 'block';
                document.getElementById('editTitle').value = shopData.settings.title;
                document.getElementById('editLogo').value = shopData.settings.logo;
                document.getElementById('editCover').value = shopData.settings.cover;
            } else {
                document.getElementById('errorMsg').style.display = 'block';
            }
        }

        function addProduct() {
            let title = document.getElementById('pTitle').value;
            let category = document.getElementById('pCat').value;
            let price = document.getElementById('pPrice').value || 'رایگان';
            let img = document.getElementById('pImg').value || 'https://via.placeholder.com/250';
            let link = document.getElementById('pLink').value || '#';

            if(!title) return alert('نام محصول الزامی است');

            shopData.products.push({ title, category, price, img, link });
            saveData();
            alert('محصول با موفقیت اضافه شد');
            document.getElementById('pTitle').value = '';
        }

        function addCategory() {
            let name = document.getElementById('newCat').value.trim();
            if(name && !shopData.categories.includes(name)) {
                shopData.categories.push(name);
                saveData();
                alert('دسته اضافه شد');
                document.getElementById('newCat').value = '';
            }
        }

        function saveTheme() {
            shopData.settings.title = document.getElementById('editTitle').value || shopData.settings.title;
            shopData.settings.logo = document.getElementById('editLogo').value || shopData.settings.logo;
            shopData.settings.cover = document.getElementById('editCover').value || shopData.settings.cover;
            saveData();
            alert('ظاهر فروشگاه به‌روزرسانی شد');
        }

        loadData();
    </script>
</body>
</html>
