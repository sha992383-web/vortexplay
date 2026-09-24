<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VORTEXPLAY - Royal Cyber Empire</title>
    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-database.js"></script>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        :root {
            --bg-deep: #030508;
            --panel-bg: rgba(13, 17, 23, 0.95);
            --royal-gold: #f59e0b;
            --royal-gold-glow: rgba(245, 158, 11, 0.4);
            --accent-cyan: #06b6d4;
            --text-main: #f3f4f6;
        }
        body {
            background: radial-gradient(circle at center, #111827 0%, var(--bg-deep) 100%);
            color: var(--text-main);
            font-family: Tahoma, sans-serif;
            min-height: 100vh;
            margin: 0;
            padding: 20px 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .main-container {
            width: 100%;
            max-width: 500px;
            text-align: center;
            padding-bottom: 60px;
        }
        .royal-crest {
            width: 130px;
            height: 130px;
            margin: 20px auto 15px auto;
            border-radius: 50%;
            border: 3px solid var(--royal-gold);
            box-shadow: 0 0 35px var(--royal-gold-glow);
            display: flex;
            align-items: center;
            justify-content: center;
            background: #000;
            font-size: 3.5rem;
            overflow: hidden;
            position: relative;
        }
        .royal-crest img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .royal-crest::after {
            content: '';
            position: absolute;
            inset: 0;
            border-radius: 50%;
            border: 1px dashed rgba(245, 158, 11, 0.5);
            animation: rotateCrest 15s linear infinite;
        }
        @keyframes rotateCrest {
            100% { transform: rotate(360deg); }
        }
        h1 {
            font-weight: 900;
            letter-spacing: 3px;
            color: var(--royal-gold);
            margin-bottom: 5px;
            font-size: 2rem;
            text-shadow: 0 0 15px var(--royal-gold-glow);
        }
        .subtitle {
            color: var(--accent-cyan);
            font-size: 0.8rem;
            letter-spacing: 3px;
            margin-bottom: 25px;
            text-transform: uppercase;
        }
        .status-shield {
            border: 1px solid var(--royal-gold);
            border-radius: 25px;
            padding: 6px 20px;
            font-size: 0.75rem;
            font-weight: bold;
            color: var(--royal-gold);
            background: rgba(245, 158, 11, 0.08);
            box-shadow: 0 0 15px rgba(245, 158, 11, 0.2);
            display: inline-block;
            margin-bottom: 30px;
        }
        .category-card {
            background: var(--panel-bg);
            border: 1px solid rgba(245, 158, 11, 0.3);
            border-radius: 16px;
            padding: 18px 22px;
            margin-bottom: 15px;
            text-align: right;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.6);
            transition: all 0.3s ease;
            cursor: pointer;
            display: block;
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }
        .category-card:hover {
            border-color: var(--royal-gold);
            box-shadow: 0 0 25px var(--royal-gold-glow);
            transform: translateY(-3px);
        }
        .category-card::before {
            content: '';
            position: absolute;
            right: 0;
            top: 0;
            height: 100%;
            width: 4px;
            background: var(--royal-gold);
        }
        .category-title {
            color: var(--royal-gold);
            font-weight: bold;
            font-size: 1.1rem;
            margin-bottom: 4px;
        }
        .category-desc {
            color: #9ca3af;
            font-size: 0.8rem;
            margin: 0;
        }
        .msg-card {
            background: var(--panel-bg);
            border: 1px solid rgba(6, 182, 212, 0.3);
            border-radius: 14px;
            padding: 18px;
            margin-bottom: 18px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
            word-break: break-word;
            text-align: right;
            position: relative;
        }
        .msg-card::before {
            content: '';
            position: absolute;
            right: 0;
            top: 0;
            height: 100%;
            width: 4px;
            background: var(--accent-cyan);
        }
        .msg-date {
            font-size: 0.7rem;
            color: #9ca3af;
            margin-top: 10px;
            text-align: left;
        }
        .msg-img {
            width: 100%;
            border-radius: 10px;
            margin-top: 12px;
            border: 1px solid var(--accent-cyan);
            max-height: 350px;
            object-fit: cover;
        }
        .btn-royal {
            border: 1px solid var(--royal-gold);
            background: rgba(245, 158, 11, 0.1);
            color: var(--royal-gold);
            padding: 10px 25px;
            border-radius: 25px;
            font-size: 0.85rem;
            font-weight: bold;
            text-decoration: none;
            display: inline-block;
            margin-top: 25px;
            cursor: pointer;
            transition: 0.3s;
            box-shadow: 0 0 15px rgba(245, 158, 11, 0.2);
        }
        .btn-royal:hover {
            background: var(--royal-gold);
            color: #000;
            box-shadow: 0 0 25px var(--royal-gold-glow);
        }
        .admin-panel-box {
            background: rgba(8, 11, 18, 0.98);
            border: 2px solid var(--royal-gold);
            border-radius: 18px;
            padding: 22px;
            margin-top: 35px;
            text-align: right;
            box-shadow: 0 0 35px rgba(245, 158, 11, 0.3);
        }
        .form-control, .form-select {
            background: #030508;
            border-color: #374151;
            color: #fff;
            border-radius: 10px;
        }
        .form-control:focus, .form-select:focus {
            background: #030508;
            color: #fff;
            border-color: var(--royal-gold);
            box-shadow: 0 0 10px var(--royal-gold-glow);
        }
        .cat-admin-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #030508;
            padding: 10px 14px;
            border-radius: 10px;
            margin-bottom: 8px;
            border: 1px solid #374151;
        }
    </style>
</head>
<body>
    <div class="main-container">
        <div class="royal-crest" id="site-logo-display">👑</div>
        <h1 id="site-title-display">VORTEXPLAY</h1>
        <div class="subtitle" id="site-subtitle-display">♦ ROYAL CYBERPUNK EMPIRE ♦</div>

        <div>
            <span class="status-shield">⚜️ SECURE CLOUD GATEWAY: ONLINE ⚜️</span>
        </div>

        <div id="dynamic-content" style="width: 100%;">
            <p style="color: #9ca3af;">در حال احضار امپراتوری ابری...</p>
        </div>

        <div id="admin-trigger-container">
            <button onclick="toggleAdminPanel()" class="btn-royal">⚙️ ورود به دربار مدیریت (God Mode)</button>
        </div>

        <div id="admin-panel" class="admin-panel-box" style="display: none;">
            <h4 class="text-warning mb-3" style="font-weight: 900;">👑 تالار فرمانروایی (مدیریت کل)</h4>
            
            <div class="mb-3">
                <label class="form-label text-info">کلید امنیتی سلطنتی (رمز ۳۲ رقمی):</label>
                <input type="password" id="admin-pass-input" class="form-control" placeholder="رمز ۳۲ رقمی را وارد کنید...">
                <button onclick="verifyAdmin()" class="btn btn-warning btn-sm mt-2 w-100 fw-bold" style="border-radius: 10px;">احراز هویت فرمانروا</button>
            </div>

            <div id="admin-controls" style="display: none;">
                <hr style="border-color: var(--royal-gold);">
                
                <h6 class="text-warning">⚜️ تاج و تخت و ظاهر سایت</h6>
                <div class="mb-3">
                    <input type="text" id="cfg-title" class="form-control mb-2" placeholder="نام جدید امپراتوری">
                    <input type="text" id="cfg-subtitle" class="form-control mb-2" placeholder="لقب و شعار سلطنتی">
                    <input type="text" id="cfg-logo" class="form-control mb-2" placeholder="لینک تصویر مهر سلطنتی (URL)">
                    <button onclick="saveSiteConfig()" class="btn btn-outline-warning btn-sm w-100 mb-3" style="border-radius: 10px;">ثبت تغییرات تاج و تخت</button>
                </div>

                <hr style="border-color: #374151;">
                <h6 class="text-warning">📜 صدور فرمان و گالری سراسری</h6>
                <div class="mb-2">
                    <label class="form-label">انتخاب حوزه (دسته):</label>
                    <select id="msg-cat-select" class="form-select"></select>
                </div>
                <div class="mb-2">
                    <label class="form-label">متن فرمان:</label>
                    <textarea id="msg-text-input" class="form-control" rows="3" placeholder="متن فرمان سلطنتی..."></textarea>
                </div>
                <div class="mb-2">
                    <label class="form-label">لینک سند تصویری گالری (اختیاری):</label>
                    <input type="text" id="msg-img-input" class="form-control" placeholder="https://example.com/image.jpg">
                </div>
                <button onclick="sendNewMessage()" class="btn btn-success btn-sm w-100 fw-bold mb-3" style="border-radius: 10px;">انتشار سراسری در امپراتوری</button>

                <hr style="border-color: #374151;">
                <h6 class="text-warning">🏰 مدیریت حوزه‌ها (دسته‌بندی‌ها)</h6>
                <div class="mb-2">
                    <input type="text" id="new-cat-title" class="form-control mb-2" placeholder="نام حوزه جدید">
                    <input type="text" id="new-cat-desc" class="form-control mb-2" placeholder="شرح مختصر حوزه">
                    <button onclick="addNewCategory()" class="btn btn-primary btn-sm w-100" style="border-radius: 10px;">احداث حوزه جدید</button>
                </div>
                <div id="admin-cat-list" class="mt-3"></div>

                <button onclick="logoutAdmin()" class="btn btn-outline-danger btn-sm w-100 mt-4" style="border-radius: 10px;">بستن دربار و خروج</button>
            </div>
        </div>
    </div>

    <script>
        const SECURE_ADMIN_PASS = "vortex9999999999999999999999999999";

        const firebaseConfig = {
            databaseURL: "https://vortexplay-default-rtdb.firebaseio.com/"
        };

        if (!firebase.apps.length) {
            firebase.initializeApp(firebaseConfig);
        }
        const db = firebase.database();
        const siteRef = db.ref('vortex_royal_site');

        let globalData = {
            config: {
                title: "VORTEXPLAY",
                subtitle: "♦ ROYAL CYBERPUNK EMPIRE ♦",
                logo: ""
            },
            categories: [
                {id: "games", title: "⚔️ ROYAL GAMES", desc: "Elite Cloud & Web Games", icon: "⚔️"},
                {id: "gallery", title: "👑 IMPERIAL GALLERY", desc: "Royal Wallpapers & Arts", icon: "👑"},
                {id: "vaults", title: "💎 SECRET VAULTS", desc: "Private Scripts & Codes", icon: "💎"}
            ],
            messages: {}
        };

        siteRef.on('value', (snapshot) => {
            const data = snapshot.val();
            if (data) {
                globalData = data;
            } else {
                siteRef.set(globalData);
            }
            updateUIAppearance();
            renderRoute();
            if(document.getElementById('admin-controls').style.display === 'block') {
                updateAdminCategorySelect();
                renderAdminCategoryList();
            }
        });

        function updateUIAppearance() {
            let cfg = globalData.config || {};
            document.getElementById('site-title-display').innerText = cfg.title || "VORTEXPLAY";
            document.getElementById('site-subtitle-display').innerText = cfg.subtitle || "♦ ROYAL CYBERPUNK EMPIRE ♦";
            
            let logoBox = document.getElementById('site-logo-display');
            if (cfg.logo && cfg.logo.trim() !== "") {
                logoBox.innerHTML = `<img src="${cfg.logo}" alt="Crest">`;
            } else {
                logoBox.innerHTML = `👑`;
            }
        }

        function renderRoute() {
            const urlParams = new URLSearchParams(window.location.search);
            const catId = urlParams.get('cat');
            const container = document.getElementById('dynamic-content');
            const categories = globalData.categories || [];

            if (!catId) {
                let html = '';
                categories.forEach(cat => {
                    let msgCount = globalData.messages && globalData.messages[cat.id] ? Object.keys(globalData.messages[cat.id]).length : 0;
                    html += `
                        <a href="?cat=${cat.id}" class="category-card">
                            <div class="d-flex justify-content-between align-items-center">
                                <div>
                                    <div class="category-title">${cat.title}</div>
                                    <p class="category-desc">${cat.desc}</p>
                                    <small class="text-warning" style="font-size: 0.7rem;">اسناد ثبت شده: ${msgCount}</small>
                                </div>
                                <div style="font-size: 1.6rem;">${cat.icon || '⚜️'}</div>
                            </div>
                        </a>
                    `;
                });
                container.innerHTML = html;
            } else {
                let currentCat = categories.find(c => c.id === catId);
                let catTitle = currentCat ? currentCat.title : "اسناد";
                
                let html = `
                    <div class="d-flex justify-content-between align-items-center mb-4 pb-2 border-bottom border-warning">
                        <h4 style="color: var(--royal-gold); margin:0; font-size: 1.1rem; font-weight: bold;">${catTitle}</h4>
                        <a href="?" class="btn btn-outline-warning btn-sm" style="border-radius: 20px; font-size: 0.75rem;">⬅️ بازگشت به دربار</a>
                    </div>
                `;

                let messagesObj = globalData.messages && globalData.messages[catId] ? globalData.messages[catId] : {};
                let messages = Object.values(messagesObj);

                if (messages.length === 0) {
                    html += '<div class="text-center text-muted mt-5">هنوز فرمانی در این حوزه صادر نشده است.</div>';
                } else {
                    messages.reverse().forEach(m => {
                        let imgTag = m.imageUrl ? `<img src="${m.imageUrl}" class="msg-img" alt="Royal Asset">` : '';
                        html += `
                            <div class="msg-card">
                                <div style="font-size: 0.95rem; line-height: 1.6;">${m.text.replace(/\n/g, '<br>')}</div>
                                ${imgTag}
                                <div class="msg-date">${m.date}</div>
                            </div>
                        `;
                    });
                }
                container.innerHTML = html;
            }
        }

        function toggleAdminPanel() {
            let panel = document.getElementById('admin-panel');
            panel.style.display = panel.style.display === 'none' ? 'block' : 'none';
        }

        function verifyAdmin() {
            let pass = document.getElementById('admin-pass-input').value;
            if (pass === SECURE_ADMIN_PASS) {
                document.getElementById('admin-controls').style.display = 'block';
                alert("احراز هویت پذیرفته شد. خوش آمدید فرمانروا!");
                updateAdminCategorySelect();
                renderAdminCategoryList();
                
                document.getElementById('cfg-title').value = globalData.config.title || "";
                document.getElementById('cfg-subtitle').value = globalData.config.subtitle || "";
                document.getElementById('cfg-logo').value = globalData.config.logo || "";
            } else {
                alert("کلید امنیتی نامعتبر است! دسترسی رد شد.");
            }
        }

        function saveSiteConfig() {
            let t = document.getElementById('cfg-title').value;
            let sub = document.getElementById('cfg-subtitle').value;
            let logo = document.getElementById('cfg-logo').value;

            if(!globalData.config) globalData.config = {};
            globalData.config.title = t;
            globalData.config.subtitle = sub;
            globalData.config.logo = logo;

            siteRef.set(globalData, (error) => {
                if(error) {
                    alert("خطا در ثبت تغییرات تاج و تخت!");
                } else {
                    alert("تاج و تخت امپراتوری بروزرسانی شد!");
                }
            });
        }

        function updateAdminCategorySelect() {
            let select = document.getElementById('msg-cat-select');
            select.innerHTML = '';
            if (globalData.categories) {
                globalData.categories.forEach(cat => {
                    select.innerHTML += `<option value="${cat.id}">${cat.title}</option>`;
                });
            }
        }

        function renderAdminCategoryList() {
            let listDiv = document.getElementById('admin-cat-list');
            listDiv.innerHTML = '';
            if (globalData.categories) {
                globalData.categories.forEach((cat, index) => {
                    listDiv.innerHTML += `
                        <div class="cat-admin-item">
                            <span style="font-size: 0.85rem; color: #e5e7eb;">${cat.title}</span>
                            <button onclick="deleteCategory(${index})" class="btn btn-danger btn-sm" style="padding: 2px 8px; font-size: 0.75rem; border-radius: 6px;">عزل حوزه</button>
                        </div>
                    `;
                });
            }
        }

        function addNewCategory() {
            let t = document.getElementById('new-cat-title').value;
            let d = document.getElementById('new-cat-desc').value;
            if (t) {
                let newId = 'cat_' + Date.now();
                if (!globalData.categories) globalData.categories = [];
                globalData.categories.push({id: newId, title: t, desc: d, icon: "🛡️"});
                
                siteRef.set(globalData, (error) => {
                    if (error) {
                        alert("خطا در احداث حوزه جدید!");
                    } else {
                        document.getElementById('new-cat-title').value = '';
                        document.getElementById('new-cat-desc').value = '';
                        alert("حوزه جدید با موفقیت به امپراتوری اضافه شد!");
                    }
                });
            } else {
                alert("لطفا عنوان حوزه را وارد کنید.");
            }
        }

        function deleteCategory(index) {
            let catId = globalData.categories[index].id;
            globalData.categories.splice(index, 1);
            if (globalData.messages && globalData.messages[catId]) {
                delete globalData.messages[catId];
            }
            siteRef.set(globalData, (error) => {
                if (error) {
                    alert("خطا در حذف حوزه!");
                } else {
                    alert("حوزه مورد نظر عزل و حذف شد.");
                }
            });
        }

        function sendNewMessage() {
            let catId = document.getElementById('msg-cat-select').value;
            let text = document.getElementById('msg-text-input').value;
            let imageUrl = document.getElementById('msg-img-input').value;

            if (!text.trim() && !imageUrl.trim()) {
                alert("لطفا متن فرمان یا لینک تصویر را وارد کنید!");
                return;
            }

            if (!globalData.messages) globalData.messages = {};
            if (!globalData.messages[catId]) globalData.messages[catId] = {};

            let now = new Date().toLocaleDateString('fa-IR') + ' - ' + new Date().toLocaleTimeString('fa-IR');
            
            const newMsgRef = db.ref('vortex_royal_site/messages/' + catId).push();
            newMsgRef.set({
                text: text,
                imageUrl: imageUrl,
                date: now
            }, (error) => {
                if (error) {
                    alert("خطا در انتشار فرمان!");
                } else {
                    document.getElementById('msg-text-input').value = '';
                    document.getElementById('msg-img-input').value = '';
                    alert("فرمان سلطنتی با موفقیت در سراسر امپراتوری منتشر شد!");
                }
            });
        }

        function logoutAdmin() {
            document.getElementById('admin-controls').style.display = 'none';
            document.getElementById('admin-pass-input').value = '';
            document.getElementById('admin-panel').style.display = 'none';
        }
    </script>
</body>
</html>
