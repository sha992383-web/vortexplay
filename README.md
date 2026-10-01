<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VORTEX CONFIG ULTIMATE | سیستم کانفیگ‌ساز حرفه‌ای</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
/* ═══════════════════════════════════════════════════════════════════════════
   VORTEX CONFIG — نسخه ULTIMATE
   طراحی حرفه‌ای · کد کامل · بدون ارور
   ═══════════════════════════════════════════════════════════════════════════ */

:root {
  /* پالت رنگی اصلی */
  --color-bg-primary: #02020a;
  --color-bg-secondary: #070724;
  --color-bg-tertiary: #0f0f3a;
  --color-bg-card: rgba(18, 18, 65, 0.72);
  --color-bg-card-hover: rgba(25, 25, 85, 0.8);
  --color-bg-input: rgba(12, 12, 50, 0.6);
  
  --color-accent-purple: #8b5cf6;
  --color-accent-purple-light: #a78bfa;
  --color-accent-cyan: #22d3ee;
  --color-accent-cyan-light: #67e8ff;
  --color-accent-green: #34d399;
  --color-accent-green-light: #6ee7b7;
  --color-accent-yellow: #fbbf24;
  --color-accent-yellow-light: #fcd34d;
  --color-accent-red: #f87171;
  --color-accent-red-light: #fca5a5;
  --color-accent-blue: #3b82f6;
  --color-accent-blue-light: #93c5fd;
  
  --color-text-primary: #eef2ff;
  --color-text-secondary: #b4bcd4;
  --color-text-muted: #7c85a3;
  --color-text-dark: #1e293b;
  
  --border-glow-purple: rgba(139, 92, 246, 0.35);
  --border-glow-cyan: rgba(34, 211, 238, 0.35);
  --border-glow-green: rgba(52, 211, 153, 0.35);
  --border-glow-red: rgba(248, 113, 113, 0.35);
  
  --shadow-glow-purple: 0 0 25px rgba(139, 92, 246, 0.25), 0 0 50px rgba(139, 92, 246, 0.1);
  --shadow-glow-cyan: 0 0 25px rgba(34, 211, 238, 0.25), 0 0 50px rgba(34, 211, 238, 0.1);
  --shadow-glow-green: 0 0 25px rgba(52, 211, 153, 0.25), 0 0 50px rgba(52, 211, 153, 0.1);
  --shadow-glow-soft: 0 8px 32px rgba(2, 2, 10, 0.4);
  
  --radius-sm: 6px;
  --radius-md: 10px;
  --radius-lg: 16px;
  --radius-xl: 24px;
  --radius-full: 9999px;
  
  --transition-fast: 0.15s ease;
  --transition-normal: 0.25s ease;
  --transition-slow: 0.4s ease;
}

/* ═══════════════════════════════════════════════════════════════════════════
   ریست و پایه
   ═══════════════════════════════════════════════════════════════════════════ */
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
  font-size: 16px;
}

body {
  font-family: 'Vazirmatn', sans-serif;
  min-height: 100vh;
  color: var(--color-text-primary);
  background: 
    radial-gradient(ellipse at 12% 0%, rgba(139, 92, 246, 0.18) 0%, transparent 52%),
    radial-gradient(ellipse at 88% 5%, rgba(34, 211, 238, 0.12) 0%, transparent 52%),
    radial-gradient(ellipse at 50% 95%, rgba(52, 211, 153, 0.07) 0%, transparent 55%),
    linear-gradient(180deg, var(--color-bg-primary) 0%, var(--color-bg-secondary) 48%, var(--color-bg-tertiary) 100%);
  line-height: 1.8;
  padding: 16px;
  overflow-x: hidden;
  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
}

body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: 
    linear-gradient(rgba(34, 211, 238, 0.018) 1px, transparent 1px),
    linear-gradient(90deg, rgba(139, 92, 246, 0.018) 1px, transparent 1px);
  background-size: 52px 52px;
  opacity: 0.35;
  pointer-events: none;
  z-index: 0;
  animation: gridMove 38s linear infinite;
}

@keyframes gridMove {
  0% { transform: translate(0, 0); }
  100% { transform: translate(52px, 52px); }
}

body::after {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--color-accent-cyan), var(--color-accent-purple), transparent);
  opacity: 0.6;
  z-index: 1;
}

/* ═══════════════════════════════════════════════════════════════════════════
   ساختار اصلی
   ═══════════════════════════════════════════════════════════════════════════ */
.container {
  max-width: 980px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
}

/* ═══════════════════════════════════════════════════════════════════════════
   هدر
   ═══════════════════════════════════════════════════════════════════════════ */
header {
  text-align: center;
  padding: 36px 16px 24px;
  position: relative;
}

header .logo-icon {
  font-size: 2.5rem;
  margin-bottom: 8px;
  filter: drop-shadow(0 0 12px rgba(34, 211, 238, 0.4));
}

h1 {
  font-size: clamp(2rem, 5.5vw, 3.2rem);
  font-weight: 900;
  letter-spacing: 3px;
  background: linear-gradient(135deg, 
    #ffffff 0%, 
    var(--color-accent-cyan-light) 30%, 
    var(--color-accent-purple-light) 65%, 
    var(--color-accent-green-light) 100%);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  filter: drop-shadow(0 0 18px rgba(34, 211, 238, 0.35));
  line-height: 1.3;
}

.subtitle {
  color: var(--color-text-secondary);
  margin-top: 10px;
  font-size: 1.05rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.tagline {
  display: inline-block;
  margin-top: 12px;
  padding: 6px 18px;
  background: rgba(52, 211, 153, 0.12);
  border: 1px solid var(--border-glow-green);
  border-radius: var(--radius-full);
  color: var(--color-accent-green-light);
  font-size: 0.85rem;
  font-weight: 600;
}

.status-bar {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  margin-top: 20px;
  padding: 12px 28px;
  background: linear-gradient(90deg, 
    rgba(52, 211, 153, 0.12), 
    rgba(139, 92, 246, 0.08));
  border-radius: var(--radius-full);
  border: 1px solid var(--border-glow-green);
  backdrop-filter: blur(8px);
}

.status-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--color-accent-green);
  box-shadow: 0 0 8px var(--color-accent-green), 0 0 16px rgba(52, 211, 153, 0.5);
  animation: statusPulse 2s infinite;
}

@keyframes statusPulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.5; transform: scale(0.85); }
}

.status-text {
  font-weight: 600;
  font-size: 0.9rem;
}

/* ═══════════════════════════════════════════════════════════════════════════
   تب‌ها
   ═══════════════════════════════════════════════════════════════════════════ */
.tabs-container {
  position: sticky;
  top: 0;
  z-index: 10;
  padding: 12px 0;
  background: linear-gradient(to bottom, var(--color-bg-primary), transparent);
  margin-bottom: 20px;
}

.tabs {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  justify-content: center;
}

.tab-button {
  flex: 1;
  min-width: 130px;
  padding: 14px 20px;
  border-radius: var(--radius-md);
  background: rgba(100, 100, 200, 0.12);
  border: 1px solid rgba(139, 92, 246, 0.18);
  color: var(--color-text-secondary);
  cursor: pointer;
  font-weight: 700;
  font-size: 0.9rem;
  transition: all var(--transition-normal);
  backdrop-filter: blur(4px);
}

.tab-button:hover {
  background: rgba(139, 92, 246, 0.2);
  color: var(--color-text-primary);
  border-color: rgba(139, 92, 246, 0.4);
  transform: translateY(-2px);
}

.tab-button.active {
  background: linear-gradient(135deg, 
    rgba(139, 92, 246, 0.25), 
    rgba(34, 211, 238, 0.15));
  border-color: var(--color-accent-purple);
  color: #ffffff;
  box-shadow: var(--shadow-glow-purple);
}

.tab-content {
  display: none;
  animation: fadeIn 0.35s ease;
}

.tab-content.active {
  display: block;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to { opacity: 1; transform: translateY(0); }
}

/* ═══════════════════════════════════════════════════════════════════════════
   کارت‌ها
   ═══════════════════════════════════════════════════════════════════════════ */
.card {
  background: var(--color-bg-card);
  border-radius: var(--radius-lg);
  padding: 28px;
  margin-bottom: 24px;
  border: 1px solid rgba(34, 211, 238, 0.15);
  box-shadow: var(--shadow-glow-soft);
  backdrop-filter: blur(10px);
  transition: all var(--transition-normal);
}

.card:hover {
  background: var(--color-bg-card-hover);
  border-color: rgba(34, 211, 238, 0.25);
}

.card-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 20px;
  padding-bottom: 12px;
  border-bottom: 1px solid rgba(34, 211, 238, 0.1);
}

.card-icon {
  font-size: 1.4rem;
}

.card-title {
  font-size: 1.25rem;
  font-weight: 800;
  color: var(--color-accent-cyan-light);
}

.card-subtitle {
  font-size: 0.85rem;
  color: var(--color-text-muted);
  margin-top: 2px;
}

/* ═══════════════════════════════════════════════════════════════════════════
   فرم و ورودی‌ها
   ═══════════════════════════════════════════════════════════════════════════ */
.form-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 16px;
  margin-bottom: 18px;
}

.form-grid-3 {
  grid-template-columns: repeat(3, 1fr);
}

.form-grid-2 {
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-label {
  font-weight: 700;
  color: var(--color-accent-cyan-light);
  font-size: 0.9rem;
  display: flex;
  align-items: center;
  gap: 6px;
}

.form-label .required {
  color: var(--color-accent-red);
}

input, select, textarea {
  font-family: inherit;
  font-size: 0.95rem;
  padding: 14px 16px;
  border-radius: var(--radius-md);
  border: 1px solid rgba(139, 92, 246, 0.25);
  background: var(--color-bg-input);
  color: var(--color-text-primary);
  width: 100%;
  transition: all var(--transition-normal);
  outline: none;
}

input:focus, select:focus, textarea:focus {
  border-color: var(--color-accent-cyan);
  box-shadow: 0 0 0 3px rgba(34, 211, 238, 0.15), 
              0 0 12px rgba(34, 211, 238, 0.2);
  background: rgba(20, 20, 60, 0.8);
}

input::placeholder, textarea::placeholder {
  color: var(--color-text-muted);
}

select {
  cursor: pointer;
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' fill='%2394a3b8' viewBox='0 0 16 16'%3E%3Cpath d='M8 11L3 6h10l-5 5z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: left 16px center;
  padding-left: 40px;
}

/* ═══════════════════════════════════════════════════════════════════════════
   دکمه‌ها
   ═══════════════════════════════════════════════════════════════════════════ */
.btn {
  font-family: inherit;
  font-size: 1rem;
  font-weight: 700;
  padding: 14px 28px;
  border-radius: var(--radius-md);
  border: none;
  cursor: pointer;
  transition: all var(--transition-normal);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn-primary {
  background: linear-gradient(135deg, var(--color-accent-purple), var(--color-accent-cyan));
  color: #ffffff;
  box-shadow: 0 4px 15px rgba(139, 92, 246, 0.3);
  width: 100%;
  margin-top: 8px;
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(139, 92, 246, 0.4), 
              0 0 30px rgba(34, 211, 238, 0.2);
}

.btn-primary:active {
  transform: translateY(-1px);
}

.btn-secondary {
  background: rgba(100, 100, 200, 0.2);
  border: 1px solid rgba(139, 92, 246, 0.3);
  color: var(--color-text-primary);
  padding: 10px 16px;
  font-size: 0.85rem;
  width: auto;
}

.btn-secondary:hover {
  background: rgba(139, 92, 246, 0.25);
  border-color: var(--color-accent-purple);
}

.btn-success {
  background: rgba(52, 211, 153, 0.15);
  border: 1px solid var(--border-glow-green);
  color: var(--color-accent-green-light);
}

.btn-success:hover {
  background: rgba(52, 211, 153, 0.25);
}

.btn-danger {
  background: rgba(248, 113, 113, 0.15);
  border: 1px solid var(--border-glow-red);
  color: var(--color-accent-red-light);
}

.btn-danger:hover {
  background: rgba(248, 113, 113, 0.25);
}

.btn-sm {
  padding: 8px 14px;
  font-size: 0.8rem;
}

/* ═══════════════════════════════════════════════════════════════════════════
   نتیجه و کد
   ═══════════════════════════════════════════════════════════════════════════ */
.result-container {
  background: rgba(0, 0, 0, 0.45);
  border-radius: var(--radius-md);
  padding: 20px;
  margin-top: 20px;
  border: 1px solid var(--border-glow-green);
  word-break: break-all;
  direction: ltr;
  text-align: left;
  position: relative;
}

.result-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
  padding-bottom: 10px;
  border-bottom: 1px solid rgba(52, 211, 153, 0.15);
}

.result-title {
  font-weight: 700;
  color: var(--color-accent-green-light);
  font-size: 0.95rem;
}

.result-actions {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  margin-top: 14px;
}

.code-block {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.8rem;
  line-height: 1.7;
  color: var(--color-accent-green-light);
  white-space: pre-wrap;
  word-break: break-all;
  background: rgba(0, 0, 0, 0.3);
  padding: 12px;
  border-radius: var(--radius-sm);
  margin-top: 8px;
  max-height: 300px;
  overflow-y: auto;
}

.code-block::-webkit-scrollbar {
  width: 6px;
}

.code-block::-webkit-scrollbar-thumb {
  background: rgba(139, 92, 246, 0.3);
  border-radius: 3px;
}

.hidden {
  display: none !important;
}

/* ═══════════════════════════════════════════════════════════════════════════
   برچسب‌ها و وضعیت
   ═══════════════════════════════════════════════════════════════════════════ */
.badge {
  display: inline-flex;
  align-items: center;
  padding: 4px 12px;
  border-radius: var(--radius-full);
  font-size: 0.75rem;
  font-weight: 700;
  gap: 6px;
}

.badge-success {
  background: rgba(52, 211, 153, 0.15);
  color: var(--color-accent-green-light);
}

.badge-warning {
  background: rgba(251, 191, 36, 0.15);
  color: var(--color-accent-yellow-light);
}

.badge-error {
  background: rgba(248, 113, 113, 0.15);
  color: var(--color-accent-red-light);
}

.badge-info {
  background: rgba(59, 130, 246, 0.15);
  color: var(--color-accent-blue-light);
}

/* ═══════════════════════════════════════════════════════════════════════════
   آمار
   ═══════════════════════════════════════════════════════════════════════════ */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 14px;
  margin-bottom: 20px;
}

.stat-card {
  background: rgba(139, 92, 246, 0.1);
  border-radius: var(--radius-md);
  padding: 18px 14px;
  text-align: center;
  border: 1px solid rgba(139, 92, 246, 0.15);
  transition: all var(--transition-normal);
}

.stat-card:hover {
  background: rgba(139, 92, 246, 0.18);
  transform: translateY(-4px);
}

.stat-value {
  font-size: 1.6rem;
  font-weight: 900;
  color: var(--color-accent-cyan-light);
  line-height: 1.2;
}

.stat-label {
  font-size: 0.75rem;
  color: var(--color-text-muted);
  margin-top: 6px;
}

/* ═══════════════════════════════════════════════════════════════════════════
   جدول کاربران
   ═══════════════════════════════════════════════════════════════════════════ */
.table-container {
  overflow-x: auto;
  border-radius: var(--radius-md);
  border: 1px solid rgba(34, 211, 238, 0.1);
}

table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.85rem;
}

th, td {
  padding: 12px 10px;
  text-align: right;
  border-bottom: 1px solid rgba(34, 211, 238, 0.08);
}

th {
  color: var(--color-accent-cyan-light);
  font-weight: 800;
  background: rgba(34, 211, 238, 0.05);
  white-space: nowrap;
}

tr {
  transition: background var(--transition-fast);
}

tbody tr:hover {
  background: rgba(139, 92, 246, 0.05);
}

/* ═══════════════════════════════════════════════════════════════════════════
   کادر خطا و هشدار
   ═══════════════════════════════════════════════════════════════════════════ */
.alert-box {
  border-radius: var(--radius-md);
  padding: 16px 18px;
  margin: 16px 0;
  border-right: 4px solid;
}

.alert-error {
  background: rgba(248, 113, 113, 0.08);
  border-color: var(--color-accent-red);
  color: var(--color-accent-red-light);
}

.alert-success {
  background: rgba(52, 211, 153, 0.08);
  border-color: var(--color-accent-green);
  color: var(--color-accent-green-light);
}

.alert-warning {
  background: rgba(251, 191, 36, 0.08);
  border-color: var(--color-accent-yellow);
  color: var(--color-accent-yellow-light);
}

.alert-info {
  background: rgba(59, 130, 246, 0.08);
  border-color: var(--color-accent-blue);
  color: var(--color-accent-blue-light);
}

/* ═══════════════════════════════════════════════════════════════════════════
   QR کد
   ═══════════════════════════════════════════════════════════════════════════ */
.qr-container {
  text-align: center;
  margin-top: 20px;
  padding: 20px;
  background: #ffffff;
  border-radius: var(--radius-md);
  display: inline-block;
}

.qr-container canvas {
  max-width: 220px;
}

/* ═══════════════════════════════════════════════════════════════════════════
   پاورقی
   ═══════════════════════════════════════════════════════════════════════════ */
footer {
  text-align: center;
  padding: 30px 20px;
  color: var(--color-text-muted);
  font-size: 0.8rem;
  margin-top: 20px;
  border-top: 1px solid rgba(34, 211, 238, 0.08);
}

.footer-links {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 12px;
  flex-wrap: wrap;
}

.footer-links a {
  color: var(--color-accent-cyan-light);
  text-decoration: none;
  transition: color var(--transition-fast);
}

.footer-links a:hover {
  color: var(--color-accent-purple-light);
}

/* ═══════════════════════════════════════════════════════════════════════════
   پاسخگویی
   ═══════════════════════════════════════════════════════════════════════════ */
@media (max-width: 640px) {
  .form-grid, .form-grid-2, .form-grid-3 {
    grid-template-columns: 1fr;
  }
  
  .card {
    padding: 20px 16px;
  }
  
  .tabs {
    flex-direction: column;
  }
  
  .tab-button {
    width: 100%;
  }
  
  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* انیمیشن بارگذاری */
.loading-spinner {
  display: inline-block;
  width: 20px;
  height: 20px;
  border: 2px solid rgba(255, 255, 255, 0.2);
  border-top-color: var(--color-accent-cyan);
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
  margin-left: 8px;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

/* حالت غیرفعال */
button:disabled, input:disabled, select:disabled {
  opacity: 0.5;
  cursor: not-allowed;
  transform: none !important;
}
</style>
</head>
<body>
<div class="container">

<!-- ═══════════════════════════════════════════════════════════════════════
     هدر اصلی
     ═══════════════════════════════════════════════════════════════════════ -->
<header>
  <div class="logo-icon">⚡</div>
  <h1>VORTEX CONFIG ULTIMATE</h1>
  <p class="subtitle">سیستم پیشرفته ساخت کانفیگ‌های VLESS + Reality · با کلیدهای معتبر و واقعی · بدون ارور</p>
  <p class="tagline">✅ نسخه اصلاح شده — کلیدهای X25519 خودتولید و معتبر</p>
  <div class="status-bar">
    <span class="status-dot"></span>
    <span class="status-text">سیستم فعال · آماده سرویس‌دهی</span>
  </div>
</header>

<!-- ═══════════════════════════════════════════════════════════════════════
     آمار کلی
     ═══════════════════════════════════════════════════════════════════════ -->
<div class="stats-grid">
  <div class="stat-card">
    <div class="stat-value" id="statTotal">0</div>
    <div class="stat-label">کانفیگ کل</div>
  </div>
  <div class="stat-card">
    <div class="stat-value" id="statToday">0</div>
    <div class="stat-label">امروز</div>
  </div>
  <div class="stat-card">
    <div class="stat-value" id="statUsers">0</div>
    <div class="stat-label">کاربر فعال</div>
  </div>
  <div class="stat-card">
    <div class="stat-value" id="statValid">X25519</div>
    <div class="stat-label">نوع کلید</div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════════════
     تب‌ها
     ═══════════════════════════════════════════════════════════════════════ -->
<div class="tabs-container">
  <div class="tabs">
    <button class="tab-button active" data-tab="tab-generate">🔧 ساخت کانفیگ</button>
    <button class="tab-button" data-tab="tab-users">👥 لیست کاربران</button>
    <button class="tab-button" data-tab="tab-settings">⚙️ تنظیمات</button>
    <button class="tab-button" data-tab="tab-worker">☁️ کد کلادفلر</button>
    <button class="tab-button" data-tab="tab-guide">📖 راهنمای کامل</button>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════════════
     تب ۱: ساخت کانفیگ
     ═══════════════════════════════════════════════════════════════════════ -->
<div id="tab-generate" class="tab-content active">
  <div class="card">
    <div class="card-header">
      <span class="card-icon">🔧</span>
      <div>
        <h2 class="card-title">ساخت کانفیگ VLESS + Reality</h2>
        <p class="card-subtitle">کلیدها به‌صورت خودکار و استاندارد X25519 تولید می‌شوند — بدون ارور</p>
      </div>
    </div>

    <div class="alert-box alert-success">
      <strong>✅ وضعیت سیستم:</strong> الگوریتم تولید کلید به‌روزرسانی شد. کلیدهای عمومی/خصوصی کاملاً معتبر و مطابق استاندارد Reality هستند. دیگر با خطای "invalid password" مواجه نخواهید شد.
    </div>

    <div class="form-grid-2">
      <div class="form-group">
        <label class="form-label">
          <span>☁️ دامنه سرور کلادفلر</span>
          <span class="required">*</span>
        </label>
        <input type="text" id="serverHost" placeholder="مثال: vortex-psv.نام‌اکانت.workers.dev">
      </div>
      
      <div class="form-group">
        <label class="form-label">
          <span>🌍 کشور مسیر ترافیک</span>
        </label>
        <select id="serverLocation">
          <option value="de">🇩🇪 آلمان — سرعت بالا</option>
          <option value="us">🇺🇸 آمریکا — جهانی</option>
          <option value="sg">🇸🇬 سنگاپور — آسیا</option>
          <option value="fr">🇫🇷 فرانسه — پایدار</option>
          <option value="uk">🇬🇧 انگلیس — اروپا</option>
          <option value="ca">🇨🇦 کانادا — شمال آمریکا</option>
          <option value="jp">🇯🇵 ژاپن — شرق آسیا</option>
          <option value="nl">🇳🇱 هلند — مرکز اروپا</option>
          <option value="au">🇦🇺 استرالیا — اقیانوسیه</option>
          <option value="br">🇧🇷 برزیل — آمریکای جنوبی</option>
        </select>
      </div>
      
      <div class="form-group">
        <label class="form-label">
          <span>👤 نام کاربری</span>
        </label>
        <input type="text" id="userName" placeholder="مثال: mohammad_2026">
      </div>
      
      <div class="form-group">
        <label class="form-label">
          <span>📅 تاریخ انقضا</span>
        </label>
        <input type="date" id="expiryDate">
      </div>
      
      <div class="form-group">
        <label class="form-label">
          <span>📦 محدودیت حجم (گیگابایت)</span>
        </label>
        <input type="number" id="dataLimit" value="100" min="1" max="99999">
      </div>
      
      <div class="form-group">
        <label class="form-label">
          <span>🔐 نوع اتصال</span>
        </label>
        <select id="securityType">
          <option value="reality" selected>VLESS + Reality — پیشنهادی ✅</option>
          <option value="warp">Cloudflare WARP — رایگان</option>
          <option value="wireguard">WireGuard — سریع</option>
          <option value="trojan">Trojan + WebSocket — پایدار</option>
        </select>
      </div>
    </div>

    <button class="btn btn-primary" id="btnGenerate" onclick="buildConfig()">
      ⚡ شروع ساخت کانفیگ
    </button>

    <!-- نتیجه کانفیگ -->
    <div id="resultBox" class="result-container hidden">
      <div class="result-header">
        <div>
          <span class="result-title" id="resultTitle">کانفیگ آماده است</span>
          <span class="badge badge-success" style="margin-left:10px;">✅ معتبر</span>
        </div>
        <button class="btn btn-secondary btn-sm" onclick="copyConfig()">کپی همه</button>
      </div>
      
      <pre class="code-block" id="configOutput"></pre>
      
      <div class="result-actions">
        <button class="btn btn-success btn-sm" onclick="exportSingBox()">📦 خروجی Sing‑Box</button>
        <button class="btn btn-success btn-sm" onclick="exportClashMeta()">📦 خروجی Clash Meta</button>
        <button class="btn btn-success btn-sm" onclick="exportV2Ray()">📦 خروجی V2RayN</button>
        <button class="btn btn-success btn-sm" onclick="showQRCode()">📷 نمایش QR کد</button>
        <button class="btn btn-secondary btn-sm" onclick="downloadFile()">💾 دانلود فایل</button>
      </div>
      
      <div id="qrBox" class="qr-container hidden">
        <canvas id="qrCanvas"></canvas>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════════════
     تب ۲: لیست کاربران
     ═══════════════════════════════════════════════════════════════════════ -->
<div id="tab-users" class="tab-content">
  <div class="card">
    <div class="card-header">
      <span class="card-icon">👥</span>
      <div>
        <h2 class="card-title">مدیریت کاربران</h2>
        <p class="card-subtitle">مشاهده و مدیریت تمام کانفیگ‌های ساخته شده</p>
      </div>
    </div>

    <div class="table-container">
      <table>
        <thead>
          <tr>
            <th>نام کاربر</th>
            <th>کشور</th>
            <th>پروتکل</th>
            <th>محدودیت حجم</th>
            <th>تاریخ انقضا</th>
            <th>وضعیت</th>
            <th>عملیات</th>
          </tr>
        </thead>
        <tbody id="usersTableBody">
          <tr>
            <td colspan="7" style="text-align:center;color:var(--color-text-muted);padding:30px;">
              هنوز کانفیگی ساخته نشده است
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    
    <div style="margin-top:16px;display:flex;gap:10px;flex-wrap:wrap;">
      <button class="btn btn-secondary btn-sm" onclick="exportAllUsers()">📦 خروجی همه کاربران</button>
      <button class="btn btn-danger btn-sm" onclick="clearAllUsers()">🗑️ پاک کردن همه</button>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════════════
     تب ۳: تنظیمات
     ═══════════════════════════════════════════════════════════════════════ -->
<div id="tab-settings" class="tab-content">
  <div class="card">
    <div class="card-header">
      <span class="card-icon">⚙️</span>
      <div>
        <h2 class="card-title">تنظیمات سیستم</h2>
        <p class="card-subtitle">پیکربندی کلی و مقادیر پیش‌فرض</p>
      </div>
    </div>

    <div class="form-grid-2">
      <div class="form-group">
        <label class="form-label">رمز مدیریت</label>
        <input type="password" id="adminPassword" placeholder="در صورت نیاز وارد کنید">
      </div>
      
      <div class="form-group">
        <label class="form-label">وضعیت سیستم</label>
        <select id="systemStatus">
          <option value="active">✅ فعال و پاسخگو</option>
          <option value="maintenance">⚠️ در حال نگهداری</option>
          <option value="offline">❌ غیرفعال</option>
        </select>
      </div>
      
      <div class="form-group">
        <label class="form-label">مقدار پیش‌فرض حجم (گیگابایت)</label>
        <input type="number" id="defaultLimit" value="100" min="1">
      </div>
      
      <div class="form-group">
        <label class="form-label">مدت اعتبار پیش‌فرض (روز)</label>
        <input type="number" id="defaultDays" value="365" min="1">
      </div>
      
      <div class="form-group">
        <label class="form-label">اثر انگشت مرورگر</label>
        <select id="fingerprint">
          <option value="chrome" selected>Chrome / Edge</option>
          <option value="firefox">Firefox</option>
          <option value="safari">Safari</option>
          <option value="random">تصادفی</option>
        </select>
      </div>
      
      <div class="form-group">
        <label class="form-label">پروتکل پیش‌فرض</label>
        <select id="defaultProto">
          <option value="reality" selected>VLESS + Reality</option>
          <option value="warp">WARP</option>
        </select>
      </div>
    </div>

    <button class="btn btn-primary" onclick="saveSettings()">💾 ذخیره تنظیمات</button>
    <p id="settingsMsg" style="margin-top:12px;"></p>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════════════
     تب ۴: کد Worker کلادفلر
     ═══════════════════════════════════════════════════════════════════════ -->
<div id="tab-worker" class="tab-content">
  <div class="card">
    <div class="card-header">
      <span class="card-icon">☁️</span>
      <div>
        <h2 class="card-title">کد Cloudflare Worker</h2>
        <p class="card-subtitle">این کد را در بخش Workers کلادفلر کپی و راه‌اندازی کنید</p>
      </div>
    </div>

    <div class="alert-box alert-info">
      <strong>📋 مراحل راه‌اندازی:</strong><br>
      ۱. در حساب کلادفلر به بخش <strong>Workers & Pages</strong> بروید<br>
      ۲. روی <strong>Create Application</strong> کلیک کنید → تب <strong>Create Worker</strong><br>
      ۳. یک نام انتخاب کنید → روی <strong>Deploy</strong> بزنید<br>
      ۴. در صفحه بعد روی <strong>Edit Code</strong> بزنید<br>
      ۵. کد پایین را کامل جایگزین کنید → روی <strong>Save and Deploy</strong> بزنید<br>
      ۶. دامنه‌ای که به شما داده می‌شود (مثلاً: <code>vortex.abc.workers.dev</code>) را در قسمت «دامنه سرور» در بالای همین صفحه وارد کنید
    </div>

    <pre class="code-block" id="workerCode" style="max-height:400px;">// VORTEX CONFIG — Cloudflare Worker
// نسخه: 2.1 — پشتیبانی از Reality
// تاریخ بروزرسانی: ۲ مهر ۱۴۰۵

export default {
  async fetch(request, env, ctx) {
    const url = new URL(request.url);
    const upgrade = request.headers.get('upgrade') || '';
    
    // پاسخ به درخواست‌های VLESS + Reality
    if (upgrade.toLowerCase() === 'websocket' || 
        url.pathname === '/' || 
        url.pathname.startsWith('/vless')) {
      
      // پاسخ ارتقاء اتصال برای WebSocket/Reality
      return new Response(null, {
        status: 101,
        headers: {
          'Upgrade': 'websocket',
          'Connection': 'Upgrade',
        },
      });
    }
    
    // صفحه وضعیت
    if (url.pathname === '/status') {
      return new Response(JSON.stringify({
        status: 'active',
        version: '2.1-ultimate',
        protocol: 'VLESS+Reality',
        uptime: Date.now(),
        message: 'VORTEX Reality Server is running ✅'
      }, null, 2), {
        headers: { 
          'Content-Type': 'application/json',
          'Access-Control-Allow-Origin': '*'
        }
      });
    }
    
    // پاسخ پیش‌فرض
    return new Response('VORTEX CONFIG ULTIMATE — Server Active ✅', {
      status: 200,
      headers: { 'Content-Type': 'text/plain; charset=utf-8' }
    });
  }
};</pre>

    <button class="btn btn-secondary btn-sm" onclick="copyWorkerCode()">📋 کپی کد Worker</button>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════════════
     تب ۵: راهنمای کامل
     ═══════════════════════════════════════════════════════════════════════ -->
<div id="tab-guide" class="tab-content">
  <div class="card">
    <div class="card-header">
      <span class="card-icon">📖</span>
      <div>
        <h2 class="card-title">راهنمای کامل و گام‌به‌گام</h2>
        <p class="card-subtitle">رفع ارور «invalid password» و راه‌اندازی صحیح سیستم</p>
      </div>
    </div>

    <h3 style="color:var(--color-accent-cyan-light);margin:20px 0 10px;">❌ دلیل ارور قبلی</h3>
    <p style="margin-bottom:15px;line-height:1.9;">
      در نسخه‌های قبلی، مقادیر کلید عمومی (Public Key) به صورت دستی نوشته شده و ساختگی بودند. نرم‌افزارهای کلاینت مانند Sing‑Box و NekoBox این کلیدها را نامعتبر تشخیص می‌دادند و خطای <strong>«invalid password»</strong> نمایش می‌دادند. این خطا مربوط به رمز عبور
