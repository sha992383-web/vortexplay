const CONFIG = {
  ADMIN_PASSWORD: 'vortex2026',
  PANEL_PATH: '/vortex',
  PORT: 443,
  ALPN: ['h2', 'http/1.1'],
  FINGERPRINT: 'chrome',
  SNI_LIST: ['www.microsoft.com', 'www.cloudflare.com', 'apple.com'],
  DEFAULT_EXPIRE_DAYS: 365,
  MAX_USERS: 50
};

// ========== توابع کمکی ==========
function generateUUID() {
  return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, c => {
    const r = Math.random() * 16 | 0;
    const v = c === 'x' ? r : (r & 0x3 | 0x8);
    return v.toString(16);
  });
}

function generateShortID() {
  const arr = new Uint8Array(8);
  crypto.getRandomValues(arr);
  return Array.from(arr, b => b.toString(16).padStart(2, '0')).join('');
}

async function generateX25519Pair() {
  const keypair = await crypto.subtle.generateKey(
    { name: 'X25519' }, true, ['deriveKey']
  );
  const pubRaw = await crypto.subtle.exportKey('raw', keypair.publicKey);
  return btoa(String.fromCharCode(...new Uint8Array(pubRaw)))
    .replace(/\+/g, '-').replace(/\//g, '_').replace(/=/g, '');
}

function getRandomSNI() {
  return CONFIG.SNI_LIST[Math.floor(Math.random() * CONFIG.SNI_LIST.length)];
}

function formatDate(timestamp) {
  if (!timestamp) return 'نامحدود';
  const d = new Date(timestamp);
  return d.toLocaleDateString('fa-IR') + ' — ' + d.toLocaleTimeString('fa-IR', { hour: '2-digit', minute: '2-digit' });
}

// ========== مدیریت کاربران ==========
async function getUsers(env) {
  const data = await env.VORTEX_KV.get('users');
  return data ? JSON.parse(data) : [];
}

async function saveUsers(env, users) {
  await env.VORTEX_KV.put('users', JSON.stringify(users));
}

async function createUser(env, host, name, days) {
  const users = await getUsers(env);
  if (users.length >= CONFIG.MAX_USERS) return { error: '❌ تعداد کاربران به حداکثر رسید' };

  const uuid = generateUUID();
  const shortId = generateShortID();
  const publicKey = await generateX25519Pair();
  const sni = getRandomSNI();
  const createdAt = Date.now();
  const expiresAt = days ? createdAt + days * 86400000 : null;

  const link = `vless://${uuid}@${host}:${CONFIG.PORT}?path=${encodeURIComponent(CONFIG.PANEL_PATH)}&security=reality&encryption=none&alpn=${CONFIG.ALPN.join(',')}&pbk=${publicKey}&fp=${CONFIG.FINGERPRINT}&sni=${sni}&sid=${shortId}&spk=${publicKey}&flow=xtls-rprx-vision#VORTEX-${encodeURIComponent(name)}`;

  users.push({
    id: generateUUID(), name, uuid, shortId, publicKey, sni, link,
    createdAt, expiresAt, active: true
  });
  await saveUsers(env, users);
  return { link };
}

async function deleteUser(env, userId) {
  let users = await getUsers(env);
  users = users.filter(u => u.id !== userId);
  await saveUsers(env, users);
}

// ========== صفحه ورود — تمام صفحه ==========
function renderLogin() {
  return `<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>VORTEX PRO ⚡</title>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;600;700;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{height:100%;min-height:100vh}
body{
  font-family:'Vazirmatn',sans-serif;
  background:linear-gradient(135deg,#020617 0%,#0f172a 40%,#1e1b4b 100%);
  min-height:100vh;
  display:flex;align-items:center;justify-content:center;
  padding:20px;color:#fff
}
.box{
  width:100%;max-width:420px;
  background:rgba(15,23,42,.85);
  border-radius:28px;
  padding:40px 30px;
  border:1px solid rgba(34,211,238,.25);
  box-shadow:0 25px 70px rgba(34,211,238,.12);
  backdrop-filter:blur(12px)
}
h1{
  font-size:2.2rem;font-weight:900;
  background:linear-gradient(135deg,#7c3aed,#22d3ee);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  text-align:center;margin-bottom:10px
}
.desc{color:#94a3b8;text-align:center;margin-bottom:35px;font-size:1rem;line-height:1.6}
.input-wrap{margin-bottom:25px}
label{display:block;margin-bottom:10px;color:#cbd5f0;font-weight:600;font-size:.95rem}
input{
  width:100%;padding:16px 20px;border-radius:14px;border:2px solid rgba(129,140,248,.3);
  background:rgba(30,41,59,.6);color:#fff;font-size:1.05rem;outline:none;
  transition:.3s
}
input:focus{border-color:#22d3ee;box-shadow:0 0 0 4px rgba(34,211,238,.15)}
button{
  width:100%;padding:16px;border-radius:14px;border:none;
  background:linear-gradient(135deg,#7c3aed,#22d3ee);
  color:#fff;font-weight:800;font-size:1.05rem;cursor:pointer;
  transition:.3s;box-shadow:0 6px 20px rgba(124,58,237,.25)
}
button:active{transform:scale(.97)}
</style>
</head>
<body>
<div class="box">
  <h1>⚡ VORTEX PRO</h1>
  <p class="desc">پنل مدیریت فیلترشکن<br>ورود با رمز عبور</p>
  <form method="get">
    <div class="input-wrap">
      <label>🔐 رمز پنل</label>
      <input type="password" name="token" placeholder="رمز را وارد کنید..." required autocomplete="current-password">
    </div>
    <button type="submit">ورود به سیستم</button>
  </form>
</div>
</body>
</html>`;
}

// ========== صفحه پنل — موبایل‌اول ==========
function renderPanel(host, users, message = '', msgType = '') {
  const subLink = `https://${host}${CONFIG.PANEL_PATH}/sub?token=${CONFIG.ADMIN_PASSWORD}`;
  return `<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>VORTEX PRO PANEL</title>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;600;700;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{height:100%}
body{
  font-family:'Vazirmatn',sans-serif;
  background:radial-gradient(ellipse at 15% 0%,rgba(124,58,237,.18)0%,transparent 50%),
              radial-gradient(ellipse at 85% 10%,rgba(34,211,238,.12)0%,transparent 50%),
              linear-gradient(180deg,#020617 0%,#0f172a 50%,#1e1b4b 100%);
  color:#f8fafc;min-height:100vh;padding:15px 12px;line-height:1.7
}
.container{max-width:100%;margin:0 auto}
header{text-align:center;margin-bottom:25px;padding:15px 5px}
h1{
  font-size:1.7rem;font-weight:900;
  background:linear-gradient(135deg,#7c3aed,#22d3ee);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  margin-bottom:5px
}
.subtitle{color:#94a3b8;font-size:.9rem}
.card{
  background:rgba(15,23,42,.8);border-radius:22px;padding:22px 18px;margin-bottom:18px;
  border:1px solid rgba(34,211,238,.18);backdrop-filter:blur(10px)
}
h2{font-size:1.15rem;color:#22d3ee;margin-bottom:16px;display:flex;align-items:center;gap:8px}
h2 span{font-size:1.3rem}
.grid{display:grid;grid-template-columns:1fr;gap:14px}
label{font-weight:600;color:#e0e7ff;display:block;margin:12px 0 6px;font-size:.92rem}
input{
  width:100%;padding:14px 16px;border-radius:12px;border:2px solid rgba(124,58,237,.3);
  background:rgba(30,41,59,.6);color:#fff;font-size:1rem;outline:none;transition:.25s
}
input:focus{border-color:#22d3ee;box-shadow:0 0 0 3px rgba(34,211,238,.15)}
button{
  padding:14px 20px;border-radius:12px;border:none;font-weight:700;font-size:.98rem;cursor:pointer;
  transition:.2s;font-family:inherit;display:inline-flex;align-items:center;justify-content:center;gap:8px
}
.btn-primary{
  background:linear-gradient(135deg,#7c3aed,#22d3ee);color:#fff;width:100%;margin-top:6px;
  box-shadow:0 5px 15px rgba(124,58,237,.25)
}
.btn-primary:active{transform:scale(.97)}
.btn-secondary{background:rgba(51,65,85,.6);color:#e0e7ff;margin:6px 4px 0 0;border:1px solid rgba(148,163,184,.2)}
.btn-danger{background:rgba(220,38,38,.15);color:#fca5a5;border:1px solid rgba(220,38,38,.25)}
.alert{
  padding:14px 16px;border-radius:12px;margin:14px 0;font-weight:500;
  display:${message?'block':'none'};font-size:.95rem
}
.alert-success{background:rgba(16,185,129,.1);border:1px solid rgba(16,185,129,.25);color:#6ee7aa}
.alert-error{background:rgba(239,68,68,.1);border:1px solid rgba(239,68,68,.25);color:#fca5a5}
.code{
  background:rgba(0,0,0,.45);padding:14px;border-radius:10px;direction:ltr;text-align:left;
  overflow-x:auto;margin:10px 0;font-size:.8rem;color:#6ee7aa;word-break:break-all;line-height:1.5
}
table{width:100%;border-collapse:collapse;margin-top:10px;display:block;overflow-x:auto}
th,td{padding:10px 8px;text-align:right;border-bottom:1px solid rgba(255,255,255,.05);font-size:.85rem}
th{color:#22d3ee;font-weight:700;white-space:nowrap}
td{white-space:nowrap}
.badge{display:inline-block;padding:4px 10px;border-radius:20px;font-size:.7rem;font-weight:700}
.badge-active{background:rgba(16,185,129,.15);color:#6ee7aa}
.badge-expired{background:rgba(245,158,11,.15);color:#fcd34d}
ul{color:#94a3b8;line-height:2.1;margin-top:8px;padding-right:5px}
ul li{margin-bottom:4px}
strong{color:#6ee7aa}
form.inline{display:inline}
</style>
</head>
<body>
<div class="container">
  <header>
    <h1>⚡ VORTEX PRO</h1>
    <p class="subtitle">مدیریت فیلترشکن VLESS+Reality</p>
  </header>

  ${message?`<div class="alert ${msgType==='success'?'alert-success':'alert-error'}">${message}</div>`:''}

  <div class="card">
    <h2>➕ ساخت کاربر جدید</h2>
    <form method="post" action="${CONFIG.PANEL_PATH}/new?token=${CONFIG.ADMIN_PASSWORD}">
      <div class="grid">
        <div>
          <label>نام کاربر</label>
          <input type="text" name="name" placeholder="مثال: تلفن همراه" required>
        </div>
        <div>
          <label>تاریخ انقضا (روز)</label>
          <input type="number" name="days" value="${CONFIG.DEFAULT_EXPIRE_DAYS}" min="1">
        </div>
      </div>
      <button type="submit" class="btn-primary">✅ ایجاد کانفیگ</button>
    </form>
  </div>

  <div class="card">
    <h2>📋 لینک سابسکریپشن</h2>
    <div class="code">${subLink}</div>
    <button class="btn-secondary" onclick="navigator.clipboard.writeText('${subLink}').then(()=>alert('✅ کپی شد!'))">📋 کپی لینک</button>
  </div>

  <div class="card">
    <h2>👥 کاربران (${users.length} نفر)</h2>
    ${users.length===0?'<p style="color:#94a3b8;padding:10px 5px">هنوز کاربری ایجاد نشده است</p>':`
    <table>
      <thead>
        <tr>
          <th>نام</th>
          <th>وضعیت</th>
          <th>عملیات</th>
        </tr>
      </thead>
      <tbody>
        ${users.map(u=>{
          const exp=u.expiresAt&&Date.now()>u.expiresAt;
          return `<tr>
            <td><strong>${u.name}</strong></td>
            <td><span class="badge ${exp?'badge-expired':'badge-active'}">${exp?'منقضی':'فعال ✅'}</span></td>
            <td>
              <button class="btn-secondary" style="padding:8px 12px;font-size:.8rem" onclick="navigator.clipboard.writeText('${u.link}').then(()=>alert('✅ کپی شد!'))">کپی</button>
              <form method="post" action="${CONFIG.PANEL_PATH}/delete?id=${u.id}&token=${CONFIG.ADMIN_PASSWORD}" class="inline" onsubmit="return confirm('آیا مطمئن هستید؟')">
                <button type="submit" class="btn-danger" style="padding:8px 12px;font-size:.8rem">حذف</button>
              </form>
            </td>
          </tr>`;
        }).join('')}
      </tbody>
    </table>`}
  </div>

  <div class="card">
    <h2>ℹ️ اطلاعات سرور</h2>
    <ul>
      <li>🔹 پروتکل: <strong>VLESS + Reality + Vision</strong></li>
      <li>🔹 پورت: <strong>${CONFIG.PORT}</strong></li>
      <li>🔹 SNI: <strong>${CONFIG.SNI_LIST[0]}</strong></li>
      <li>🔹 Fingerprint: <strong>${CONFIG.FINGERPRINT}</strong></li>
      <li>🔹 دامنه: <strong>${host}</strong></li>
    </ul>
  </div>
</div>
</body>
</html>`;
}

// ========== مسیرهای اصلی ==========
export default {
  async fetch(request, env, ctx) {
    const url = new URL(request.url);
    const host = url.hostname;
    const path = url.pathname;
    const token = url.searchParams.get('token') || '';
    const isAuth = token === CONFIG.ADMIN_PASSWORD;

    // اتصال WebSocket
    if (path.startsWith(CONFIG.PANEL_PATH)) {
      const upgrade = request.headers.get('upgrade') || '';
      if (upgrade.toLowerCase() === 'websocket') {
        return new Response(null, { status: 101, headers: { Upgrade: 'websocket', Connection: 'Upgrade' } });
      }
    }

    // صفحه ورود / پنل
    if (path === CONFIG.PANEL_PATH || path === CONFIG.PANEL_PATH + '/') {
      if (!isAuth) return new Response(renderLogin(), { headers: { 'Content-Type': 'text/html;charset=utf-8' } });
      return new Response(renderPanel(host, await getUsers(env)), { headers: { 'Content-Type': 'text/html;charset=utf-8' } });
    }

    // ساخت کاربر
    if (path === CONFIG.PANEL_PATH + '/new' && request.method === 'POST' && isAuth) {
      const form = await request.formData();
      const name = form.get('name') || 'کاربر';
      const days = parseInt(form.get('days')) || CONFIG.DEFAULT_EXPIRE_DAYS;
      const res = await createUser(env, host, name, days);
      const users = await getUsers(env);
      return new Response(renderPanel(host, users, res.error || `✅ کاربر «${name}» ایجاد شد! لینک را از جدول کپی کنید`, res.error?'error':'success'), { headers: { 'Content-Type': 'text/html;charset=utf-8' } });
    }

    // حذف کاربر
    if (path === CONFIG.PANEL_PATH + '/delete' && request.method === 'POST' && isAuth) {
      await deleteUser(env, url.searchParams.get('id'));
      return new Response(renderPanel(host, await getUsers(env), '✅ کاربر با موفقیت حذف شد', 'success'), { headers: { 'Content-Type': 'text/html;charset=utf-8' } });
    }

    // سابسکریپشن
    if (path === CONFIG.PANEL_PATH + '/sub') {
      const users = await getUsers(env);
      const active = users.filter(u => u.active && (!u.expiresAt || Date.now() < u.expiresAt));
      return new Response(active.map(u => u.link).join('\n'), { headers: { 'Content-Type': 'text/plain;charset=utf-8' } });
    }

    // صفحه اصلی
    return new Response('VORTEX PRO — Active ✅', { status: 200 });
  }
};
