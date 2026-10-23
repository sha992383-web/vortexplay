<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vortex VPN - پنل دریافت کانفیگ</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: Tahoma, sans-serif; }
        body { background: #090d16; color: #fff; display: flex; justify-content: center; align-items: center; min-height: 100vh; }
        .container { background: #111827; padding: 30px; border-radius: 16px; width: 100%; max-width: 420px; box-shadow: 0 10px 30px rgba(0,0,0,0.8); border: 1px solid #1f2937; text-align: center; }
        h2 { color: #38bdf8; margin-bottom: 8px; font-size: 22px; }
        p { color: #9ca3af; font-size: 13px; margin-bottom: 20px; }
        .input-group { text-align: right; margin-bottom: 15px; }
        label { font-size: 12px; color: #d1d5db; display: block; margin-bottom: 5px; }
        input, select { width: 100%; padding: 12px; border-radius: 8px; border: 1px solid #374151; background: #1f2937; color: #fff; font-size: 14px; outline: none; }
        input:focus, select:focus { border-color: #38bdf8; }
        button { background: linear-gradient(135deg, #0284c7, #2563eb); color: white; border: none; padding: 12px; border-radius: 8px; cursor: pointer; font-weight: bold; width: 100%; font-size: 16px; margin-top: 10px; transition: 0.3s; }
        button:hover { opacity: 0.9; transform: translateY(-1px); }
        .result { background: #0f172a; padding: 15px; margin-top: 20px; border-radius: 8px; word-break: break-all; border: 1px dashed #38bdf8; display: none; text-align: right; }
        .result span { font-size: 12px; color: #38bdf8; display: block; margin-bottom: 5px; }
        .result input { font-size: 11px; background: #020617; padding: 8px; }
        .copy-btn { background: #16a34a; margin-top: 8px; padding: 8px; font-size: 14px; }
        .copy-btn:hover { background: #15803d; }
    </style>
</head>
<body>

    <div class="container">
        <h2>⚡ Vortex VPN</h2>
        <p>سیستم هوشمند ساخت کانفیگ رایگان و پرسرعت</p>
        
        <div class="input-group">
            <label>نام دلخواه کانفیگ:</label>
            <input type="text" id="configName" placeholder="مثلاً: My_Phone">
        </div>

        <div class="input-group">
            <label>حجم دلخواه:</label>
            <select id="configTraffic">
                <option value="50GB">۵۰ گیگابایت (استاندارد)</option>
                <option value="100GB">۱۰۰ گیگابایت (پیشنهادی)</option>
                <option value="Unlimited">نامحدود (VIP)</option>
            </select>
        </div>

        <button onclick="generateConfig()">ساخت و دریافت کانفیگ</button>
        
        <div id="output" class="result">
            <span>🔗 لینک اتصال شما (برای کپی کلیک کنید):</span>
            <input type="text" id="configLink" readonly onclick="copyConfig()">
            <button class="copy-btn" onclick="copyConfig()">کپی کردن کانفیگ</button>
        </div>
    </div>

    <script>
        function generateUUID() {
            return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, function(c) {
                var r = Math.random() * 16 | 0, v = c == 'x' ? r : (r & 0x3 | 0x8);
                return v.toString(16);
            });
        }

        function generateConfig() {
            const name = document.getElementById('configName').value.trim() || 'Vortex-User';
            const traffic = document.getElementById('configTraffic').value;
            const uuid = generateUUID();
            const host = window.location.host; 

            // ساخت ساختار کانفیگ حرفه‌ای
            const config = `vless://${uuid}@${host}:443?encryption=none&security=tls&sni=${host}&type=ws&path=%2F#${encodeURIComponent(name + ' [' + traffic + ']')}`;

            document.getElementById('output').style.display = 'block';
            document.getElementById('configLink').value = config;
        }

        function copyConfig() {
            const copyText = document.getElementById("configLink");
            copyText.select();
            copyText.setSelectionRange(0, 99999);
            navigator.clipboard.writeText(copyText.value);
            alert("کانفیگ با موفقیت کپی شد! در v2rayNG یا V2Box وارد کنید.");
        }
    </script>

</body>
</html>
