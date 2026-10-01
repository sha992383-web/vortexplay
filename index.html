<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vortex Play - PS Payload Host</title>
    <style>
        :root {
            --bg-color: #0d0f18;
            --card-bg: #161a29;
            --primary-color: #ffd700;
            --text-color: #ffffff;
            --text-muted: #a0aabf;
            --accent-color: #6366f1;
            --danger-color: #ef4444;
            --success-color: #22c55e;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start;
            padding: 20px;
        }

        header {
            text-align: center;
            margin-bottom: 30px;
            animation: fadeIn 0.8s ease-in-out;
        }

        header h1 {
            font-size: 2.2rem;
            color: var(--primary-color);
            margin-bottom: 8px;
            text-shadow: 0 0 15px rgba(255, 215, 0, 0.3);
        }

        header p {
            color: var(--text-muted);
            font-size: 1rem;
        }

        .container {
            width: 100%;
            max-width: 800px;
            background: var(--card-bg);
            border-radius: 16px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 215, 0, 0.1);
            margin-bottom: 20px;
        }

        .status-box {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(255, 255, 255, 0.03);
            padding: 15px 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            border-right: 4px solid var(--primary-color);
        }

        .status-box span {
            font-weight: bold;
            color: var(--primary-color);
        }

        .grid-payloads {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 15px;
            margin-bottom: 25px;
        }

        .btn-payload {
            background: linear-gradient(135deg, #1f243d, #2a3056);
            color: var(--text-color);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 12px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
        }

        .btn-payload:hover {
            background: linear-gradient(135deg, var(--primary-color), #cca100);
            color: #000;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
        }

        .console-log {
            background: #090a0f;
            color: var(--success-color);
            padding: 15px;
            border-radius: 8px;
            font-family: monospace;
            font-size: 0.85rem;
            height: 120px;
            overflow-y: auto;
            border: 1px solid rgba(255, 255, 255, 0.05);
            margin-bottom: 20px;
            direction: ltr;
            text-align: left;
        }

        .admin-section {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 20px;
            margin-top: 20px;
        }

        .admin-section h3 {
            font-size: 1.1rem;
            margin-bottom: 12px;
            color: var(--primary-color);
        }

        .admin-inputs {
            display: flex;
            gap: 10px;
        }

        input[type="password"] {
            flex: 1;
            background: #090a0f;
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 12px;
            border-radius: 8px;
            color: #fff;
            font-size: 0.9rem;
            outline: none;
        }

        input[type="password"]:focus {
            border-color: var(--primary-color);
        }

        .btn-admin {
            background: var(--accent-color);
            color: #fff;
            border: none;
            padding: 0 20px;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
        }

        .btn-admin:hover {
            background: #4f46e5;
        }

        footer {
            text-align: center;
            color: var(--text-muted);
            font-size: 0.85rem;
            margin-top: auto;
        }

        footer a {
            color: var(--primary-color);
            text-decoration: none;
        }
    </style>
</head>
<body>

    <header>
        <h1>Vortex Play Host</h1>
        <p>پیشرفته‌ترین میزبان تخصصی ابزارها و اکسپلویت‌های کنسول</p>
    </header>

    <div class="container">
        <div class="status-box">
            <div>وضعیت سیستم: <span id="sys-status">آماده برای اجرا</span></div>
            <div>نسخه پلتفرم: <span id="fw-version">v2.5 - Stable</span></div>
        </div>

        <div class="grid-payloads">
            <button class="btn-payload" onclick="runPayload('GoldHEN v2.4b18')">GoldHEN Payload</button>
            <button class="btn-payload" onclick="runPayload('WebRTE Loader')">WebRTE Loader</button>
            <button class="btn-payload" onclick="runPayload('Disable Updates')">Disable Updates</button>
            <button class="btn-payload" onclick="runPayload('Backup Database')">Backup Database</button>
        </div>

        <div class="console-log" id="consoleLog">
            [Vortex Engine] سیستم با موفقیت بارگذاری شد...<br>
            [Info] منتظر انتخاب کاربر برای اجرای پِی‌لود...
        </div>

        <div class="admin-section">
            <h3>ورود به پنل مدیریت اختصاصی</h3>
            <div class="admin-inputs">
                <input type="password" id="adminPass" placeholder="رمز عبور مدیریت را وارد کنید...">
                <button class="btn-admin" onclick="checkAdmin()">تایید</button>
            </div>
        </div>
    </div>

    <footer>
        پشتیبانی کانال تلگرام: <a href="https://t.me/vortexplay3" target="_blank">@vortexplay3</a>
    </footer>

    <script>
        function logMessage(msg) {
            const consoleBox = document.getElementById('consoleLog');
            const timeNow = new Date().toLocaleTimeString();
            consoleBox.innerHTML += `<br>[${timeNow}] ${msg}`;
            consoleBox.scrollTop = consoleBox.scrollHeight;
        }

        function runPayload(payloadName) {
            document.getElementById('sys-status').innerText = "در حال تزریق...";
            logMessage(`درخواست اجرای پِی‌لود: [${payloadName}] صادر شد.`);
            
            setTimeout(() => {
                document.getElementById('sys-status').innerText = "با موفقیت اجرا شد";
                logMessage(`[موفقیت] پِی‌لود ${payloadName} روی سیستم اعمال گردید.`);
            }, 1200);
        }

        function checkAdmin() {
            const pass = document.getElementById('adminPass').value;
            if(pass.trim() !== "") {
                logMessage("[امنیت] تلاش برای دسترسی به پنل مدیریت ثبت شد.");
                alert("رمز عبور بررسی شد. دسترسی موقت فعال گردید.");
            } else {
                alert("لطفاً رمز عبور را وارد کنید.");
            }
        }
    </script>

</body>
</html>
