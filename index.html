<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>فروشگاه VORTEXPLAY</title>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #f39c12;
            --bg: #0d0714;
            --card-bg: #170d24;
            --border: #f39c12;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Vazirmatn', sans-serif; }

        body {
            background-color: var(--bg);
            color: #fff;
            padding-bottom: 80px;
        }

        header {
            text-align: center;
            padding: 25px 15px;
            background: rgba(0,0,0,0.3);
        }

        .logo {
            width: 90px; height: 90px;
            border-radius: 50%;
            border: 3px solid var(--primary);
            object-fit: cover;
            margin-bottom: 10px;
        }

        h1 { color: var(--primary); font-size: 1.8rem; }

        .cover-box {
            max-width: 900px;
            margin: 15px auto;
            padding: 0 15px;
        }

        .cover-box img {
            width: 100%;
            max-height: 250px;
            object-fit: cover;
            border-radius: 12px;
            border: 1px solid var(--primary);
        }

        .container {
            max-width: 900px;
            margin: 20px auto;
            padding: 0 15px;
        }

        /* دسته‌بندی‌ها */
        .cat-bar {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 10px;
            margin-bottom: 20px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .cat-item {
            background: rgba(255,255,255,0.1);
            color: #fff;
            border: none;
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            white-space: nowrap;
        }

        .cat-item.active {
            background: var(--primary);
            color: #000;
            font-weight: bold;
        }

        /* کارت محصولات */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 15px;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--primary);
            border-radius: 12px;
            padding: 12px;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .card img {
            width: 100%;
            height: 140px;
            object-fit: cover;
            border-radius: 8px;
            margin-bottom: 10px;
        }

        .price {
            color: var(--primary);
            font-weight: bold;
            margin: 8px 0;
        }

        .btn-dl {
            background: var(--primary);
            color: #000;
            text-decoration: none;
            padding: 8px;
            border-radius: 6px;
            font-weight: bold;
            display: block;
        }

        /* نوار مدیریت پایین */
        .admin-bar {
            position: fixed;
            bottom: 0; left: 0; right: 0;
            background: #000;
            border-top: 1px solid var(--primary);
            padding: 10px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .btn-admin {
            background: var(--primary);
            border: none;
            padding: 8px 15px;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
        }

        /* پنجره مدال */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.85);
            z-index: 999;
            padding: 20px;
            overflow-y: auto;
        }

        .modal-box {
            background: #170d24;
            border: 2px solid var(--primary);
            border-radius: 12px;
            max-width: 450px;
            margin: 30px auto;
            padding: 20px;
            position: relative;
        }

        .close { position: absolute; left: 15px; top: 10px; cursor: pointer; font-size: 1.5rem; }

        input, select {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            background: #000;
            border: 1px solid var(--primary);
            color: #fff;
            border-radius: 6px;
            outline: none;
        }
    </style>
</head>
<body>

    <header>
        <img id="logoImg" class="logo" src="https://via.placeholder.com/90/f39c12/000000?text=LOGO" alt="لوگو">
        <h1 id="shopTitle">فروشگاه VORTEXPLAY</h1>
    </header>

    <div class="cover-box">
        <img id="coverImg" src="https://via.placeholder.com/900x250/170d24/f39c12?text=VORTEXPLAY+STORE" alt="کاور">
    </div>

    <div class="container">
        <div class="cat-bar" id="catBar"></div>
        <div class="grid" id="productGrid"></div>
    </div>

    <div class="admin-bar">
        <span>🛒 فروشگاه فعال است</span>
        <button class="btn-admin" onclick="showModal()">⚙️ مدیریت</button>
    </div>

    <!-- مدال ورود و تنظیمات -->
    <div id="modal" class="modal">
        <div class="modal-box">
            <span class="close" onclick="hideModal()">&times;</span>

            <!-- بخش فرم ورود -->
            <div id="loginBox">
                <h3 style="color:var(--primary); margin-bottom:15px;">ورود به مدیریت</h3>
                <input type="text" id="passInput" placeholder="رمز عبور (1234)">
                <button class="btn-admin" style="width:100%;" onclick="login()">ورود</button>
                <p id="alertMsg" style="color:red; display:none; margin-top:10px; text-align:center;">رمز اشتباه است!</p>
            </div>

            <!-- بخش پنل مدیریت -->
            <div id="panelBox" style="display:none;">
                <h3 style="color:var(--primary); margin-bottom:10px;">➕ افزودن محصول</h3>
                <input type="text" id="pTitle" placeholder="عنوان محصول">
                <select id="pCat"></select>
                <input type="text" id="pPrice" placeholder="قیمت (مثلا: ۵۰,۰۰۰ تومان)">
                <input type="text" id="pImg" placeholder="لینک عکس محصول">
                <input type="text" id="pLink" placeholder="لینک دانلود/خرید">
                <button class="btn-admin" style="width:100%; background:#27ae60; color:#fff;" onclick="newProduct()">انتشار محصول</button>

                <hr style="border-color:var(--primary); margin:15px 0;">

                <h3 style="color:var(--primary); margin-bottom:10px;">📁 افزودن دسته‌بندی</h3>
                <input type="text" id="cName" placeholder="نام دسته جدید">
                <button class="btn-admin" style="width:100%;" onclick="newCategory()">افزودن دسته</button>

                <hr style="border-color:var(--primary); margin:15px 0;">

                <h3 style="color:var(--primary); margin-bottom:10px;">🎨 تغییر ظاهر</h3>
                <input type="text" id="sTitle" placeholder="نام فروشگاه">
                <input type="text" id="sLogo" placeholder="لینک لوگو">
                <input type="text" id="sCover" placeholder="لینک کاور">
                <button class="btn-admin" style="width:100%; background:#e67e22; color:#fff;" onclick="updateTheme()">ذخیره تغییرات ظاهر</button>
            </div>
        </div>
    </div>

    <script>
        // داده‌های فروشگاه
        let db = {
            title: "فروشگاه VORTEXPLAY",
            logo: "https://via.placeholder.com/90/f39c12/000000?text=LOGO",
            cover: "https://via.placeholder.com/900x250/170d24/f39c12?text=VORTEXPLAY+STORE",
            categories: ["همه", "برنامه‌ها", "بازی‌ها"],
            currentCat: "همه",
            items: []
        };

        // بارگیری داده‌ها از حافظه
        function load() {
            let data = localStorage.getItem('vortex_simple_db');
            if(data) db = JSON.parse(data);
            render();
        }

        // ذخیره داده‌ها
        function save() {
            localStorage.setItem('vortex_simple_db', JSON.stringify(db));
            render();
        }

        // نمایش اطلاعات در صفحه
        function render() {
            document.getElementById('shopTitle').innerText = db.title;
            document.getElementById('logoImg').src = db.logo;
            document.getElementById('coverImg').src = db.cover;

            // ساخت منوی دسته‌بندی
            let catBar = document.getElementById('catBar');
            let pCat = document.getElementById('pCat');
            catBar.innerHTML = '';
            pCat.innerHTML = '';

            db.categories.forEach(cat => {
                let btn = document.createElement('button');
                btn.className = `cat-item ${db.currentCat === cat ? 'active' : ''}`;
                btn.innerText = cat;
                btn.onclick = () => { db.currentCat = cat; render(); };
                catBar.appendChild(btn);

                if(cat !== "همه") {
                    pCat.innerHTML += `<option value="${cat}">${cat}</option>`;
                }
            });

            // ساخت لیست محصولات
            let grid = document.getElementById('productGrid');
            grid.innerHTML = '';

            let list = db.currentCat === "همه" 
                ? db.items 
                : db.items.filter(x => x.cat === db.currentCat);

            if(list.length === 0) {
                grid.innerHTML = '<p style="grid-column: 1/-1; text-align:center; color:#888;">محصولی وجود ندارد.</p>';
            }

            list.forEach(item => {
                grid.innerHTML += `
                    <div class="card">
                        <img src="${item.img || 'https://via.placeholder.com/200'}" alt="عکس">
                        <h4>${item.title}</h4>
                        <div class="price">${item.price}</div>
                        <a href="${item.link}" target="_blank" class="btn-dl">📥 دریافت / دانلود</a>
                    </div>
                `;
            });
        }

        // ورود ساده به مدیریت
        function login() {
            let pass = document.getElementById('passInput').value.trim();
            // تبدیل اعداد فارسی به انگلیسی
            pass = pass.replace(/[۰-۹]/g, d => "۰۱۲۳۴۵۶۷۸۹".indexOf(d));

            if(pass === "1234") {
                document.getElementById('loginBox').style.display = 'none';
                document.getElementById('panelBox').style.display = 'block';
                document.getElementById('sTitle').value = db.title;
                document.getElementById('sLogo').value = db.logo;
                document.getElementById('sCover').value = db.cover;
            } else {
                document.getElementById('alertMsg').style.display = 'block';
            }
        }

        // افزودن محصول جدید
        function newProduct() {
            let title = document.getElementById('pTitle').value;
            let cat = document.getElementById('pCat').value;
            let price = document.getElementById('pPrice').value || 'رایگان';
            let img = document.getElementById('pImg').value;
            let link = document.getElementById('pLink').value || '#';

            if(!title) return alert('عنوان محصول را بنویسید');

            db.items.push({ title, cat, price, img, link });
            save();
            alert('محصول اضافه شد!');
            document.getElementById('pTitle').value = '';
        }

        // افزودن دسته‌بندی
        function newCategory() {
            let name = document.getElementById('cName').value.trim();
            if(name && !db.categories.includes(name)) {
                db.categories.push(name);
                save();
                alert('دسته اضافه شد!');
                document.getElementById('cName').value = '';
            }
        }

        // ویرایش ظاهر
        function updateTheme() {
            db.title = document.getElementById('sTitle').value || db.title;
            db.logo = document.getElementById('sLogo').value || db.logo;
            db.cover = document.getElementById('sCover').value || db.cover;
            save();
            alert('تغییرات ظاهر ذخیره شد!');
        }

        function showModal() { document.getElementById('modal').style.display = 'block'; }
        function hideModal() { document.getElementById('modal').style.display = 'none'; }

        load();
    </script>
</body>
</html>
