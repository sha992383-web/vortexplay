import os
import sqlite3
from datetime import datetime
from functools import wraps
from flask import Flask, render_template_string, request, jsonify, session

app = Flask(__name__)
# کلید امنیتی نشست‌ها
app.secret_key = os.urandom(24)

# رمز عبور پنل مدیریت (قابل تغییر)
ADMIN_PASSWORD = "32_CHAR_ROYAL_VORTEX_SECRET_KEY_2026"
DATABASE = 'vortexplay.db'

def get_db():
    conn = sqlite3.connect(DATABASE)
    conn.row_factory = sqlite3.Row
    return conn

def init_db():
    """ایجاد جداول دیتابیس و داده‌های پیش‌فرض در صورت عدم وجود"""
    with get_db() as conn:
        cursor = conn.cursor()
        
        cursor.execute('''
            CREATE TABLE IF NOT EXISTS settings (
                key TEXT PRIMARY KEY,
                value TEXT
            )
        ''')
        
        cursor.execute('''
            CREATE TABLE IF NOT EXISTS categories (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                name TEXT NOT NULL,
                icon TEXT NOT NULL
            )
        ''')
        
        cursor.execute('''
            CREATE TABLE IF NOT EXISTS items (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                category_id INTEGER,
                title TEXT NOT NULL,
                description TEXT,
                image_url TEXT,
                download_link TEXT,
                FOREIGN KEY (category_id) REFERENCES categories (id)
            )
        ''')
        
        cursor.execute('''
            CREATE TABLE IF NOT EXISTS products (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                title TEXT NOT NULL,
                description TEXT,
                price TEXT NOT NULL,
                image_url TEXT,
                link TEXT
            )
        ''')
        
        cursor.execute('''
            CREATE TABLE IF NOT EXISTS messages (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                sender_name TEXT NOT NULL,
                content TEXT NOT NULL,
                created_at TEXT NOT NULL
            )
        ''')

        cursor.execute('SELECT COUNT(*) FROM settings')
        if cursor.fetchone()[0] == 0:
            defaults = {
                'title': 'VORTEXPLAY',
                'subtitle': 'پادشاهی نهایی گیمرها ✨',
                'logo_url': 'https://via.placeholder.com/150/d4af37/000000?text=VORTEX',
                'cover_url': 'https://via.placeholder.com/800x400/1a0933/d4af37?text=VORTEXPLAY+ROYAL+GAMING',
                'bg_url': ''
            }
            for k, v in defaults.items():
                cursor.execute('INSERT INTO settings (key, value) VALUES (?, ?)', (k, v))
            
            cursor.execute('INSERT INTO categories (name, icon) VALUES (?, ?)', ('بازی‌ها', '🎮'))
            cursor.execute('INSERT INTO categories (name, icon) VALUES (?, ?)', ('نرم‌افزارها', '💻'))
            cursor.execute('INSERT INTO categories (name, icon) VALUES (?, ?)', ('اکانت‌ها', '🔑'))
            cursor.execute('INSERT INTO categories (name, icon) VALUES (?, ?)', ('آموزش‌ها', '📜'))
            
        conn.commit()

def admin_required(f):
    @wraps(f)
    def decorated_function(*args, **kwargs):
        if not session.get('is_admin'):
            return jsonify({'status': 'error', 'message': 'دسترسی غیرمجاز!'}), 403
        return f(*args, **kwargs)
    return decorated_function

# --- API ROUTES ---

@app.route('/api/data', methods=['GET'])
def get_site_data():
    conn = get_db()
    cursor = conn.cursor()
    
    settings = dict(cursor.execute('SELECT key, value FROM settings').fetchall())
    categories = [dict(row) for row in cursor.execute('SELECT * FROM categories').fetchall()]
    items = [dict(row) for row in cursor.execute('SELECT * FROM items').fetchall()]
    products = [dict(row) for row in cursor.execute('SELECT * FROM products').fetchall()]
    
    for cat in categories:
        cat['count'] = sum(1 for item in items if item['category_id'] == cat['id'])

    return jsonify({
        'settings': settings,
        'categories': categories,
        'items': items,
        'products': products
    })

@app.route('/api/login', methods=['POST'])
def login():
    data = request.json or {}
    if data.get('password') == ADMIN_PASSWORD:
        session['is_admin'] = True
        return jsonify({'status': 'success', 'message': 'ورود موفقیت‌آمیز پادشاه!'})
    return jsonify({'status': 'error', 'message': 'رمز عبور اشتباه است!'}), 401

@app.route('/api/logout', methods=['POST'])
def logout():
    session.pop('is_admin', None)
    return jsonify({'status': 'success'})

@app.route('/api/message', methods=['POST'])
def send_message():
    data = request.json or {}
    name = data.get('name', 'ناشناس').strip()
    content = data.get('content', '').strip()
    
    if not content:
        return jsonify({'status': 'error', 'message': 'متن پیام نمی‌تواند خالی باشد!'}), 400
        
    date_str = datetime.now().strftime("%Y-%m-%d %H:%M")
    with get_db() as conn:
        conn.cursor().execute(
            'INSERT INTO messages (sender_name, content, created_at) VALUES (?, ?, ?)',
            (name, content, date_str)
        )
        conn.commit()
    return jsonify({'status': 'success', 'message': 'پیام شما با موفقیت ارسال شد ✨'})

@app.route('/api/admin/settings', methods=['POST'])
@admin_required
def update_settings():
    data = request.json or {}
    with get_db() as conn:
        cursor = conn.cursor()
        for key, value in data.items():
            cursor.execute('UPDATE settings SET value = ? WHERE key = ?', (value, key))
        conn.commit()
    return jsonify({'status': 'success', 'message': 'تنظیمات با موفقیت تأیید و اعمال شد!'})

@app.route('/api/admin/product', methods=['POST'])
@admin_required
def add_product():
    data = request.json or {}
    with get_db() as conn:
        conn.cursor().execute(
            'INSERT INTO products (title, description, price, image_url, link) VALUES (?, ?, ?, ?, ?)',
            (data.get('title'), data.get('description'), data.get('price'), data.get('image_url'), data.get('link'))
        )
        conn.commit()
    return jsonify({'status': 'success', 'message': 'محصول با موفقیت قرار گرفت!'})

@app.route('/api/admin/messages', methods=['GET'])
@admin_required
def get_messages():
    conn = get_db()
    messages = [dict(row) for row in conn.cursor().execute('SELECT * FROM messages ORDER BY id DESC').fetchall()]
    return jsonify({'status': 'success', 'messages': messages})

# --- FRONTEND ROUTE ---

HTML_TEMPLATE = """
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VORTEXPLAY — پادشاهی گیمینگ</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700&family=Vazirmatn:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #d4af37;
            --gold-light: #fff2a3;
            --bg-dark: #0b0314;
            --purple-card: rgba(25, 10, 45, 0.75);
            --border-gold: rgba(212, 175, 55, 0.4);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Vazirmatn', sans-serif; }

        body {
            background-color: var(--bg-dark);
            color: #fff;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
            padding-bottom: 90px;
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }

        .bg-glow {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 20%, rgba(106, 13, 173, 0.25) 0%, rgba(11, 3, 20, 0.95) 80%);
            z-index: -2;
            pointer-events: none;
        }

        #particles {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: var(--gold-light);
            border-radius: 50%;
            box-shadow: 0 0 8px var(--gold);
            animation: flyUp linear infinite;
        }

        @keyframes flyUp {
            0% { transform: translateY(100vh) scale(0); opacity: 0; }
            50% { opacity: 0.8; }
            100% { transform: translateY(-10vh) scale(1); opacity: 0; }
        }

        header { text-align: center; padding: 40px 20px 20px; }

        .crown {
            font-size: 3rem;
            animation: floatCrown 3s ease-in-out infinite;
            display: inline-block;
            filter: drop-shadow(0 0 15px var(--gold));
        }

        @keyframes floatCrown {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .logo-container {
            width: 120px; height: 120px;
            margin: 15px auto;
            position: relative;
            border-radius: 50%;
            padding: 5px;
        }

        .logo-container::before {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            border-radius: 50%;
            border: 2px dashed var(--gold);
            animation: spinRing 12s linear infinite;
        }

        @keyframes spinRing { 100% { transform: rotate(360deg); } }

        .logo-img {
            width: 100%; height: 100%;
            border-radius: 50%;
            object-fit: cover;
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.5);
        }

        h1 {
            font-family: 'Cinzel', 'Vazirmatn', serif;
            color: var(--gold-light);
            text-shadow: 0 0 15px var(--gold);
            font-size: 2.5rem;
            margin-top: 10px;
        }

        .subtitle { color: #d1c4e9; font-size: 1rem; margin-top: 5px; }

        .cover-box { max-width: 900px; margin: 20px auto; padding: 0 20px; }

        .cover-img {
            width: 100%;
            border-radius: 15px;
            border: 2px solid var(--gold);
            box-shadow: 0 0 25px rgba(212, 175, 55, 0.3);
            max-height: 380px;
            object-fit: cover;
        }

        .container { max-width: 1000px; margin: 30px auto; padding: 0 20px; }

        .section-title {
            color: var(--gold);
            border-bottom: 2px solid var(--border-gold);
            padding-bottom: 8px;
            margin-bottom: 20px;
            font-size: 1.4rem;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 20px;
        }

        .card {
            background: var(--purple-card);
            border: 1px solid var(--border-gold);
            border-radius: 12px;
            padding: 15px;
            backdrop-filter: blur(10px);
            transition: all 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(212, 175, 55, 0.4);
            border-color: var(--gold);
        }

        .card img {
            width: 100%; height: 150px;
            object-fit: cover;
            border-radius: 8px;
            margin-bottom: 10px;
        }

        .price-tag {
            background: linear-gradient(45deg, var(--gold), #b38728);
            color: #000;
            font-weight: bold;
            padding: 4px 10px;
            border-radius: 6px;
            font-size: 0.85rem;
            display: inline-block;
            margin-bottom: 10px;
        }

        .price-tag.free { background: #2e7d32; color: #fff; }

        .btn {
            display: block;
            width: 100%;
            padding: 10px;
            background: linear-gradient(45deg, var(--gold), #996515);
            border: none;
            color: #000;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            text-align: center;
            text-decoration: none;
        }

        .btn:hover { filter: brightness(1.2); box-shadow: 0 0 10px var(--gold); }

        .message-form {
            background: var(--purple-card);
            border: 1px solid var(--border-gold);
            padding: 20px;
            border-radius: 12px;
            margin-top: 40px;
        }

        .input-group { margin-bottom: 15px; }

        .input-group input, .input-group textarea {
            width: 100%;
            padding: 10px;
            background: rgba(0,0,0,0.5);
            border: 1px solid var(--border-gold);
            color: #fff;
            border-radius: 6px;
            outline: none;
        }

        .admin-bar {
            position: fixed;
            bottom: 0; left: 0; right: 0;
            background: rgba(11, 3, 20, 0.95);
            border-top: 2px solid var(--gold);
            padding: 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(5px);
            z-index: 200;
            overflow-y: auto;
            padding: 20px;
        }

        .modal-content {
            background: #150826;
            border: 2px solid var(--gold);
            border-radius: 12px;
            max-width: 600px;
            margin: 40px auto;
            padding: 25px;
            position: relative;
        }

        .close-btn {
            position: absolute;
            left: 15px; top: 15px;
            color: var(--gold);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .preview-box {
            background: rgba(0,0,0,0.4);
            border: 1px dashed var(--gold);
            padding: 10px;
            border-radius: 8px;
            margin: 10px 0;
            text-align: center;
        }

        .status-wait { color: #ffca28; font-size: 0.85rem; margin-top: 5px; }

        .btn-confirm { background: #2e7d32 !important; color: #fff !important; margin-top: 10px; }
    </style>
</head>
<body>
    <div class="bg-glow"></div>
    <div id="particles"></div>

    <header>
        <div class="crown">👑</div>
        <div class="logo-container">
            <img id="siteLogo" class="logo-img" src="" alt="لوگو">
        </div>
        <h1 id="siteTitle">VORTEXPLAY</h1>
        <div class="subtitle" id="siteSubtitle">پادشاهی نهایی گیمرها</div>
    </header>

    <div class="cover-box">
        <img id="siteCover" class="cover-img" src="" alt="کاور اصلی">
    </div>

    <div class="container">
        <div class="section-title">🛍️ محصولات اختصاصی</div>
        <div class="grid" id="productsGrid"></div>

        <div class="message-form">
            <div class="section-title" style="border:none;">📬 ارسال پیام به مدیر</div>
            <div class="input-group"><input type="text" id="msgName" placeholder="نام شما (اختیاری)"></div>
            <div class="input-group"><textarea id="msgContent" rows="3" placeholder="پیام خود را بنویسید..."></textarea></div>
            <button class="btn" onclick="sendMessage()">ارسال پیام ✨</button>
        </div>
    </div>

    <div class="admin-bar">
        <span style="color: var(--gold); font-size: 0.9rem;">👑 VORTEXPLAY Control Center</span>
        <button class="btn" style="width: auto; padding: 6px 15px;" onclick="toggleAdminModal()">⚙️ پنل مدیریت</button>
    </div>

    <div id="adminModal" class="modal">
        <div class="modal-content">
            <span class="close-btn" onclick="toggleAdminModal()">&times;</span>
            <h2 style="color: var(--gold); margin-bottom: 20px;">⚙️ مدیریت VORTEXPLAY</h2>

            <div id="loginForm">
                <p>لطفاً کلید مدیر را وارد کنید:</p>
                <div class="input-group" style="margin-top: 10px;">
                    <input type="password" id="adminPass" placeholder="رمز عبور...">
                </div>
                <button class="btn" onclick="loginAdmin()">ورود به پنل</button>
            </div>

            <div id="adminControls" style="display: none;">
                <div style="margin-bottom: 25px;">
                    <h3>📝 ویرایش عناوین</h3>
                    <div class="input-group"><input type="text" id="editTitle" placeholder="عنوان جدید"></div>
                    <div class="input-group"><input type="text" id="editSubtitle" placeholder="زیرعنوان جدید"></div>
                    <div class="preview-box">
                        <div id="textPreview">پیش‌نمایش: -</div>
                        <div class="status-wait">⏳ منتظر تأیید...</div>
                    </div>
                    <button class="btn btn-confirm" onclick="applySettingsText()">✅ تأیید و اعمال متن</button>
                </div>
                <hr style="border-color: var(--border-gold); margin: 15px 0;">

                <div style="margin-bottom: 25px;">
                    <h3>🛍️ افزودن محصول</h3>
                    <div class="input-group"><input type="text" id="prodTitle" placeholder="نام محصول"></div>
                    <div class="input-group"><input type="text" id="prodDesc" placeholder="توضیحات"></div>
                    <div class="input-group"><input type="text" id="prodPrice" placeholder="قیمت"></div>
                    <div class="input-group"><input type="text" id="prodImage" placeholder="لینک عکس"></div>
                    <div class="input-group"><input type="text" id="prodLink" placeholder="لینک دریافت"></div>
                    <button class="btn btn-confirm" onclick="addProduct()">✅ تأیید و افزودن محصول</button>
                </div>
                <hr style="border-color: var(--border-gold); margin: 15px 0;">

                <div>
                    <h3>📬 صندوق پیام‌ها</h3>
                    <div id="messagesList" style="margin-top: 10px; max-height: 200px; overflow-y: auto;"></div>
                </div>

                <button class="btn" style="background: #c62828; color: #fff; margin-top: 20px;" onclick="logoutAdmin()">خروج</button>
            </div>
        </div>
    </div>

    <script>
        let siteData = {};

        function createParticles() {
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
        }

        async function loadData() {
            let res = await fetch('/api/data');
            siteData = await res.json();
            
            document.getElementById('siteTitle').innerText = siteData.settings.title;
            document.getElementById('siteSubtitle').innerText = siteData.settings.subtitle;
            document.getElementById('siteLogo').src = siteData.settings.logo_url;
            document.getElementById('siteCover').src = siteData.settings.cover_url;

            let prodHtml = '';
            siteData.products.forEach(p => {
                let isFree = p.price.includes('رایگان');
                prodHtml += `
                    <div class="card">
                        <img src="${p.image_url || 'https://via.placeholder.com/250'}" alt="${p.title}">
                        <div class="price-tag ${isFree ? 'free' : ''}">${p.price}</div>
                        <h3>${p.title}</h3>
                        <p style="font-size: 0.85rem; color:#ccc; margin: 8px 0;">${p.description}</p>
                        <a href="${p.link}" target="_blank" class="btn">⬇️ دریافت</a>
                    </div>
                `;
            });
            document.getElementById('productsGrid').innerHTML = prodHtml || '<p>محصولی یافت نشد.</p>';
        }

        async function sendMessage() {
            let name = document.getElementById('msgName').value;
            let content = document.getElementById('msgContent').value;
            
            let res = await fetch('/api/message', {
                method: 'POST',
                headers: {'Content-Type': 'application/json'},
                body: JSON.stringify({name, content})
            });
            let data = await res.json();
            alert(data.message);
            if(data.status === 'success') {
                document.getElementById('msgContent').value = '';
            }
        }

        function toggleAdminModal() {
            let modal = document.getElementById('adminModal');
            modal.style.display = modal.style.display === 'block' ? 'none' : 'block';
        }

        async function loginAdmin() {
            let pass = document.getElementById('adminPass').value;
            let res = await fetch('/api/login', {
                method: 'POST',
                headers: {'Content-Type': 'application/json'},
                body: JSON.stringify({password: pass})
            });
            let data = await res.json();
            if(data.status === 'success') {
                document.getElementById('loginForm').style.display = 'none';
                document.getElementById('adminControls').style.display = 'block';
                loadAdminMessages();
            } else {
                alert(data.message);
            }
        }

        async function logoutAdmin() {
            await fetch('/api/logout', {method: 'POST'});
            location.reload();
        }

        async function applySettingsText() {
            let title = document.getElementById('editTitle').value;
            let subtitle = document.getElementById('editSubtitle').value;
            let payload = {};
            if(title) payload.title = title;
            if(subtitle) payload.subtitle = subtitle;

            let res = await fetch('/api/admin/settings', {
                method: 'POST',
                headers: {'Content-Type': 'application/json'},
                body: JSON.stringify(payload)
            });
            let data = await res.json();
            alert(data.message);
            loadData();
        }

        async function addProduct() {
            let payload = {
                title: document.getElementById('prodTitle').value,
                description: document.getElementById('prodDesc').value,
                price: document.getElementById('prodPrice').value,
                image_url: document.getElementById('prodImage').value,
                link: document.getElementById('prodLink').value
            };

            let res = await fetch('/api/admin/product', {
                method: 'POST',
                headers: {'Content-Type': 'application/json'},
                body: JSON.stringify(payload)
            });
            let data = await res.json();
            alert(data.message);
            loadData();
        }

        async function loadAdminMessages() {
            let res = await fetch('/api/admin/messages');
            let data = await res.json();
            if(data.status === 'success') {
                let html = '';
                data.messages.forEach(m => {
                    html += `
                        <div style="background:rgba(0,0,0,0.5); padding:8px; border-radius:5px; margin-bottom:5px; font-size:0.85rem;">
                            <strong>${m.sender_name}</strong> (${m.created_at}):
                            <p>${m.content}</p>
                        </div>
                    `;
                });
                document.getElementById('messagesList').innerHTML = html || 'پیامی وجود ندارد.';
            }
        }

        document.getElementById('editTitle').addEventListener('input', (e) => {
            document.getElementById('textPreview').innerText = 'پیش‌نمایش: ' + e.target.value;
        });

        createParticles();
        loadData();
    </script>
</body>
</html>
"""

@app.route('/')
def index():
    return render_template_string(HTML_TEMPLATE)

if __name__ == '__main__':
    init_db()
    print("👑 VORTEXPLAY Online! Open in Browser: http://127.0.0.1:5000")
    app.run(debug=True, port=5000)
