// ==========================================
// VORTEX PLAY - ULTIMATE CLOUDFLARE PANEL
// ==========================================

const ADMIN_TOKEN = "a1b2c3d4e5f678901234567890abcdef"; // رمز عبور ۳۲ کاراکتری مدیریت
const DEFAULT_UUID = "d342d11e-d424-4583-b36e-524ab1f0afa4";

export default {
  async fetch(request, env, ctx) {
    const url = new URL(request.url);
    const path = url.pathname;
    const host = url.host;

    // مدیریت درخواست‌های وب‌سکت VLESS
    if (request.headers.get("Upgrade") === "websocket") {
      return await handleWebSocket(request);
    }

    // صفحه اصلی / پنل مدیریت
    if (path === "/") {
      return new Response(getPanelHTML(host), {
        headers: { "Content-Type": "text/html; charset=utf-8" },
      });
    }

    // تولید لینک اشتراک (Sub)
    if (path.startsWith("/sub/")) {
      const token = path.split("/")[2];
      if (token !== ADMIN_TOKEN) {
        return new Response("Unauthorized Access", { status: 403 });
      }
      const subContent = `vless://${DEFAULT_UUID}@${host}:443?encryption=none&security=tls&sni=${host}&type=ws&path=%2F#Vortex-Play-Sub`;
      return new Response(btoa(subContent), {
        headers: { "Content-Type": "text/plain; charset=utf-8" },
      });
    }

    // API ایجاد کانفیگ جدید
    if (path === "/api/create" && request.method === "POST") {
      try {
        const body = await request.json();
        if (body.token !== ADMIN_TOKEN) {
          return new Response(JSON.stringify({ error: "Invalid Token" }), { status: 401, headers: { "Content-Type": "application/json" } });
        }
        const newUuid = generateUUID();
        const conf = `vless://${newUuid}@${host}:443?encryption=none&security=tls&sni=${host}&type=ws&path=%2F#${body.name || 'Vortex-User'}`;
        return new Response(JSON.stringify({ success: true, config: conf, uuid: newUuid }), {
          headers: { "Content-Type": "application/json" },
        });
      } catch (e) {
        return new Response(JSON.stringify({ error: "Bad Request" }), { status: 400, headers: { "Content-Type": "application/json" } });
      }
    }

    return new Response("Vortex Play Node is Active.", { status: 200 });
  },
};

async function handleWebSocket(request) {
  // شبیه‌سازی و هندلینگ پایه‌ای پروکسی ویس‌سکت
  const webSocketPair = new WebSocketPair();
  const [client, server] = Object.values(webSocketPair);
  server.accept();
  return new Response(null, {
    status: 101,
    webSocket: client,
  });
}

function generateUUID() {
  return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, function(c) {
    var r = Math.random() * 16 | 0, v = c == 'x' ? r : (r & 0x3 | 0x8);
    return v.toString(16);
  });
}

function getPanelHTML(host) {
  return `<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vortex Play - Secure Management Panel</title>
    <style>
        :root {
            --bg: #07090f;
            --card: #111522;
            --primary: #00ffcc;
            --accent: #7928ca;
            --text: #ffffff;
            --muted: #8a99ad;
            --danger: #ff3366;
            --success: #00ff66;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: monospace; }
        body { background: var(--bg); color: var(--text); min-height: 100vh; display: flex; justify-content: center; align-items: center; padding: 20px; }
        .container { width: 100%; max-width: 700px; background: var(--card); border: 1px solid rgba(0,255,204,0.3); border-radius: 16px; padding: 30px; box-shadow: 0 0 30px rgba(0,0,0,0.8); }
        h1 { color: var(--primary); font-size: 1.6rem; text-align: center; margin-bottom: 5px; text-shadow: 0 0 10px rgba(0,255,204,0.3); }
        p.subtitle { text-align: center; color: var(--muted); font-size: 0.85rem; margin-bottom: 25px; }
        
        .login-box, .panel-box { display: flex; flex-direction: column; gap: 15px; }
        .hidden { display: none !important; }
        
        label { font-size: 0.85rem; color: var(--muted); }
        input { background: #040508; border: 1px solid rgba(255,255,255,0.1); padding: 12px; border-radius: 8px; color: #fff; font-size: 0.95rem; outline: none; }
        input:focus { border-color: var(--primary); }
        
        button { background: var(--primary); color: #000; border: none; padding: 12px; border-radius: 8px; font-weight: bold; cursor: pointer; transition: 0.2s; }
        button:hover { background: #00b38f; }
        
        .output-box { background: #040508; border: 1px solid rgba(255,255,255,0.1); padding: 15px; border-radius: 8px; word-break: break-all; color: var(--success); font-size: 0.85rem; margin-top: 5px; }
        .stat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 15px; }
        .stat-card { background: rgba(0,0,0,0.4); padding: 12px; border-radius: 8px; border-left: 3px solid var(--primary); }
        .stat-card span { display: block; color: var(--primary); font-size: 1.1rem; font-weight: bold; margin-top: 5px; }
    </style>
</head>
<body>
    <div class="container">
        <h1>VORTEX PLAY PANEL</h1>
        <p class="subtitle">سیستم مدیریت متمرکز و ساخت کانفیگ اختصاصی</p>

        <!-- فرم احراز هویت با رمز ۳۲ رقمی -->
        <div id="loginSection" class="login-box">
            <label>توکن / رمز عبور ۳۲ رقمی مدیریت:</label>
            <input type="password" id="tokenInput" placeholder="رمز ۳۲ کاراکتری را وارد کنید...">
            <button onclick="login()">ورود به پنل مدیریت</button>
        </div>

        <!-- پنل اصلی مدیریت (پس از ورود موفق) -->
        <div id="panelSection" class="panel-box hidden">
            <div class="stat-grid">
                <div class="stat-card">وضعیت سرور <span style="color: var(--success);"> آنلاین و پایدار</span></div>
                <div class="stat-card">پروتکل فعال <span>VLESS + WebSocket</span></div>
            </div>

            <label>نام کاربر یا کلاینت جدید:</label>
            <input type="text" id="clientName" placeholder="مثال: Vortex_User_01">
            <button onclick="createConfig()">ساخت و تولید کانفیگ جدید</button>

            <label>خروجی کانفیگ ساخته شده:</label>
            <div class="output-box" id="configOutput">هنوز کانفیجی ساخته نشده است.</div>

            <label>لینک اشتراک کلی (Subscription):</label>
            <div class="output-box" id="subOutput">https://${host}/sub/${ADMIN_TOKEN}</div>
            
            <button style="background: var(--accent); color: #fff;" onclick="copySubLink()">کپی لینک اشتراک کل</button>
        </div>
    </div>

    <script>
        const savedToken = "${ADMIN_TOKEN}";

        function login() {
            const input = document.getElementById('tokenInput').value.trim();
            if(input === savedToken) {
                document.getElementById('loginSection').classList.add('hidden');
                document.getElementById('panelSection').classList.remove('hidden');
            } else {
                alert('رمز عبور ۳۲ رقمی اشتباه است!');
            }
        }

        async function createConfig() {
            const name = document.getElementById('clientName').value.trim() || 'Vortex-Client';
            const res = await fetch('/api/create', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ token: savedToken, name: name })
            });
            const data = await res.json();
            if(data.success) {
                document.getElementById('configOutput').innerText = data.config;
                alert('کانفیگ با موفقیت ساخته شد!');
            } else {
                alert('خطا در ساخت کانفیگ');
            }
        }

        function copySubLink() {
            const text = document.getElementById('subOutput').innerText;
            navigator.clipboard.writeText(text);
            alert('لینک اشتراک کپی شد!');
        }
    </script>
</body>
</html>`;
}
