<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#080a12">
<title>فضای شخصی علی | MYSPACE</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;700;900&display=swap" rel="stylesheet">
<style>
:root {
  --bg:#05070d;
  --panel:rgba(255,255,255,.07);
  --panel2:rgba(255,255,255,.13);
  --line:rgba(255,255,255,.15);
  --text:#f4f2ff;
  --muted:#a3a1cb;
  --purple:#a78bfa;
  --blue:#38bdf8;
  --footer-color:#2dd4bf;
  --blob1:#6366f1;
  --blob2:#0ea5e9;
  color-scheme:dark;
}
html[data-theme="light"] {
  --bg:#f1f5f9;
  --panel:rgba(255,255,255,.72);
  --panel2:rgba(255,255,255,.92);
  --line:rgba(15,23,42,.14);
  --text:#0f172a;
  --muted:#64748b;
  --purple:#7c3aed;
  --blue:#0284c7;
  --footer-color:#0d9488;
  --blob1:#c4b5fd;
  --blob2:#7dd3fc;
  color-scheme:light;
}
* { box-sizing:border-box; }
html { scroll-behavior:smooth; }
body {
  margin:0;
  min-height:100vh;
  background:var(--bg);
  background-image:
    radial-gradient(circle at 10% 15%,color-mix(in srgb,var(--blob1) 40%,transparent),transparent 45%),
    radial-gradient(circle at 90% 85%,color-mix(in srgb,var(--blob2) 35%,transparent),transparent 45%);
  background-attachment:fixed;
  color:var(--text);
  font-family:"Vazirmatn",Tahoma,Arial,sans-serif;
  line-height:1.8;
  overflow-x:hidden;
  transition:background-color .25s,color .25s;
  perspective:1200px;
}
button,input,textarea { font:inherit; }
button,a { -webkit-tap-highlight-color:transparent; }
button { touch-action:manipulation; }
a { color:var(--muted);text-decoration:none; }
a:hover { color:var(--text); }
.app-container {
  width:100%;
  max-width:520px;
  min-height:100vh;
  margin:auto;
  padding:16px;
  display:flex;
  flex-direction:column;
  position:relative;
  z-index:1;
}
.wrap { width:100%; }
header {
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
  padding:8px 4px 16px;
  flex-wrap:wrap;
}
.brand { font-size:19px;font-weight:900; animation:brandGlow 3s ease-in-out infinite; letter-spacing:1px; }
.brand span { color:var(--purple); }
@keyframes brandGlow{50%{text-shadow:0 0 18px var(--purple)}}
nav { display:flex;gap:7px;align-items:center;flex-wrap:wrap; }
.icon-button {
  width:38px;height:38px;
  border-radius:50%;
  border:1px solid var(--line);
  background:var(--panel);
  color:var(--text);
  cursor:pointer;
  display:grid;
  place-items:center;
  font-size:16px;
  backdrop-filter:blur(12px);
  transition:transform .3s cubic-bezier(.3,1.6,.5,1),background .2s,box-shadow .3s;
}
.icon-button:hover { transform:translateY(-3px) rotate(-8deg) scale(1.08);box-shadow:0 0 20px color-mix(in srgb,var(--purple) 60%,transparent); }
.icon-button:active { transform:scale(.94); }
.glass {
  position:relative;
  transform-style:preserve-3d;
  transition:transform .25s cubic-bezier(.2,.8,.2,1),box-shadow .3s;
  backdrop-filter:blur(22px) saturate(160%);
  -webkit-backdrop-filter:blur(22px) saturate(160%);
  background:linear-gradient(145deg,color-mix(in srgb,var(--panel2) 90%,transparent),var(--panel));
  border:1px solid var(--line);
  border-radius:24px;
  box-shadow:0 25px 50px -15px rgba(0,0,0,.45),inset 0 1px 0 rgba(255,255,255,.18),inset 0 -1px 0 rgba(255,255,255,.04);
}
.glass::before{
  content:"";position:absolute;inset:0;border-radius:inherit;padding:1px;
  background:conic-gradient(from var(--ang,0deg),transparent 0 60%,var(--purple),var(--blue),transparent 85%);
  -webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);
  -webkit-mask-composite:xor;mask-composite:exclude;
  animation:spinBorder 6s linear infinite;pointer-events:none;opacity:.9;
}
.glass::after{
  content:"";position:absolute;inset:0;border-radius:inherit;pointer-events:none;
  background:radial-gradient(circle at var(--mx,50%) var(--my,0%),rgba(255,255,255,.22),transparent 45%);
  opacity:var(--glare,0);transition:opacity .3s;
}
@property --ang{syntax:"<angle>";inherits:false;initial-value:0deg}
@keyframes spinBorder{to{--ang:360deg}}
.glass > *{transform:translateZ(30px)}
.overlay-panel.glass > *{transform:none}
.hero { padding:34px 18px;text-align:center;margin:10px 0 18px; }
.eyebrow { color:var(--blue);font-size:11px;letter-spacing:2px;font-weight:700; animation:heroIn .8s .1s both; }
h1 { font-size:clamp(26px,6vw,38px);line-height:1.5;margin:12px 0; animation:heroIn 1s cubic-bezier(.2,.8,.2,1) both; }
.gradient {
  background:linear-gradient(90deg,var(--purple),var(--blue),#f472b6,var(--purple));
  background-size:300% 100%;
  -webkit-background-clip:text; background-clip:text;
  -webkit-text-fill-color:transparent;
  animation:gradMove 5s linear infinite;
}
@keyframes gradMove{to{background-position:300% 0}}
p { color:var(--muted);font-size:14px; }
.hero p { animation:heroIn 1s .25s both; }
@keyframes heroIn{from{opacity:0;transform:translateY(20px);filter:blur(8px)}}
.tag {
  display:inline-block;
  padding:3px 10px;
  border:1px solid var(--line);
  border-radius:999px;
  color:var(--muted);
  font-size:11px;
  background:var(--panel);
  backdrop-filter:blur(8px);
}
.card { padding:22px;margin-bottom:16px;min-width:0; }
.card h2 { font-size:19px;margin:0 0 8px; }
.product {
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  min-height:220px;
  margin:16px auto;
}
.product-icon {
  display:inline-block;
  font-size:52px;
  animation:float3d 5s ease-in-out infinite;
  filter:drop-shadow(0 10px 20px var(--purple));
  background:linear-gradient(135deg,var(--purple),var(--blue));
  -webkit-background-clip:text;background-clip:text;
  -webkit-text-fill-color:transparent;
}
@keyframes float3d{0%,100%{transform:translateZ(50px) translateY(0) rotateY(0)}50%{transform:translateZ(60px) translateY(-10px) rotateY(180deg)}}
.price { font-size:27px;font-weight:900;margin:10px 0;color:var(--blue); text-shadow:0 0 24px color-mix(in srgb,var(--blue) 60%,transparent); }
.button {
  border:1px solid var(--line);
  background:linear-gradient(135deg,var(--purple),var(--blue));
  color:white;
  padding:11px 16px;
  border-radius:12px;
  font-weight:700;
  cursor:pointer;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  gap:8px;
  position:relative;
  overflow:hidden;
  box-shadow:0 10px 25px -8px color-mix(in srgb,var(--purple) 70%,transparent);
  transition:transform .2s,box-shadow .3s,filter .2s;
  text-align:center;
}
.button::after{
  content:"";position:absolute;top:0;left:-120%;width:60%;height:100%;
  background:linear-gradient(110deg,transparent,rgba(255,255,255,.45),transparent);
  transform:skewX(-20deg);animation:shine 3.2s ease-in-out infinite;
}
.button.secondary::after{animation-duration:4.5s}
@keyframes shine{0%,60%{left:-120%}100%{left:160%}}
.button:hover { transform:translateY(-3px);box-shadow:0 18px 35px -10px color-mix(in srgb,var(--blue) 80%,transparent); filter:brightness(1.08); }
.button:active { transform:scale(.97); }
.button:disabled { opacity:.6;cursor:wait; }
.button.secondary { background:var(--panel2);color:var(--text); }
.button.full { width:100%;margin-top:10px; }
.status { font-size:12px;min-height:24px;overflow-wrap:anywhere;color:var(--blue);margin-top:7px; }
label { display:block;font-size:12px;color:var(--muted);margin:10px 0 5px; }
input {
  width:100%;
  background:var(--panel);
  border:1px solid var(--line);
  border-radius:12px;
  padding:12px;
  color:var(--text);
  outline:none;
  transition:border-color .2s,box-shadow .3s;
}
input:focus { border-color:var(--purple); box-shadow:0 0 0 4px color-mix(in srgb,var(--purple) 25%,transparent); }
.support-card { text-align:center;margin-top:20px; }
.support-links { display:grid;grid-template-columns:1fr;gap:10px;margin-top:14px; }
footer {
  text-align:center;
  padding:20px 0 25px;
  color:var(--footer-color);
  font-size:12px;
  margin-top:auto;
  animation:heroIn 1s both;
}
.footer-name { color:var(--footer-color);font-weight:bold; }
.island-wrap {
  position:sticky;
  top:8px;
  z-index:20;
  display:flex;
  justify-content:center;
  margin:6px 0 14px;
}
.island {
  background:rgba(0,0,0,.85);
  color:#fff;
  border:1px solid rgba(255,255,255,.2);
  border-radius:999px;
  padding:10px 22px;
  min-width:185px;
  max-width:100%;
  display:flex;
  align-items:center;
  justify-content:center;
  gap:10px;
  cursor:pointer;
  user-select:none;
  box-shadow:0 10px 25px rgba(0,0,0,.35);
  backdrop-filter:blur(16px);
  transition:transform .4s cubic-bezier(.3,1.6,.5,1),box-shadow .3s;
  animation:islandIn .9s cubic-bezier(.3,1.6,.5,1);
}
.island:hover{transform:scale(1.05);box-shadow:0 15px 40px rgba(0,0,0,.5),0 0 25px color-mix(in srgb,var(--blue) 40%,transparent)}
.island:focus-visible { outline:2px solid var(--blue);outline-offset:3px; }
@keyframes islandIn{from{transform:scaleX(.3);opacity:0}}
.island-icon { font-size:16px; }
.island-main {
  font-size:14px;
  font-weight:700;
  white-space:nowrap;
  direction:ltr;
  font-variant-numeric:tabular-nums;
}
.island-sub { font-size:10px;color:#a1a1aa;white-space:nowrap; }
.island-dots { display:flex;gap:4px;margin-inline-start:5px; }
.island-dots span { width:4px;height:4px;border-radius:50%;background:#555; }
.island-dots span.active { background:#38bdf8; box-shadow:0 0 8px #38bdf8; animation:pulse 1.6s infinite; }
@keyframes pulse{50%{transform:scale(1.6)}}
[hidden] { display:none!important; }
.overlay {
  position:fixed;
  inset:0;
  z-index:100;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:16px;
}
.overlay-backdrop {
  position:absolute;
  inset:0;
  background:rgba(0,0,0,.72);
  backdrop-filter:blur(7px);
  -webkit-backdrop-filter:blur(7px);
}
.overlay-panel {
  position:relative;
  z-index:1;
  width:min(440px,100%);
  max-height:90vh;
  overflow-y:auto;
  padding:24px 20px;
  animation:popIn .2s ease;
}
.overlay-close {
  position:absolute;
  top:12px;
  left:12px;
  width:34px;
  height:34px;
  border-radius:50%;
  border:1px solid var(--line);
  background:var(--panel2);
  color:var(--text);
  cursor:pointer;
}
.dash-grid { display:grid;grid-template-columns:1fr;gap:12px;margin-top:12px; }
.dash-card { padding:15px;border-radius:16px;background:var(--panel2);border:1px solid var(--line); transition:transform .3s; }
.dash-card:hover{transform:translateY(-3px) scale(1.01)}
.dash-label { font-size:11px;color:var(--muted);margin-bottom:6px; }
.dash-value { font-size:13px;font-weight:700;overflow-wrap:anywhere; }
.dash-profile { display:flex;align-items:center;gap:12px; }
.dash-avatar {
  width:48px;height:48px;border-radius:50%;
  background:linear-gradient(135deg,var(--purple),var(--blue));
  display:grid;place-items:center;font-size:22px;flex:none;
}
.dash-id { direction:ltr;text-align:left;font-size:10px;color:var(--muted);overflow-wrap:anywhere; }
.dash-actions { display:flex;gap:8px;flex-wrap:wrap;margin-top:14px; }
.dash-actions .button { flex:1; }
@keyframes popIn {
  from { opacity:0;transform:translateY(8px) scale(.98); }
  to { opacity:1;transform:translateY(0) scale(1); }
}
nav a{position:relative;padding:2px 4px}
nav a::after{content:"";position:absolute;bottom:0;right:0;width:0;height:2px;background:linear-gradient(90deg,var(--purple),var(--blue));transition:width .3s}
nav a:hover::after{width:100%}
.fx-bg{position:fixed;inset:0;z-index:-1;overflow:hidden;pointer-events:none}
.fx-blob{position:absolute;width:60vmax;height:60vmax;border-radius:50%;filter:blur(80px);opacity:.55;mix-blend-mode:screen;animation:blobMove 18s ease-in-out infinite alternate}
.fx-blob.b1{background:var(--blob1);top:-20vmax;left:-15vmax}
.fx-blob.b2{background:var(--blob2);bottom:-25vmax;right:-15vmax;animation-delay:-6s}
.fx-blob.b3{background:var(--purple);top:30%;left:40%;width:35vmax;height:35vmax;opacity:.35;animation-duration:24s;animation-delay:-12s}
html[data-theme="light"] .fx-blob{mix-blend-mode:multiply;opacity:.4}
@keyframes blobMove{0%{transform:translate(0,0) scale(1) rotate(0)}50%{transform:translate(10vw,8vh) scale(1.15) rotate(60deg)}100%{transform:translate(-6vw,14vh) scale(.9) rotate(120deg)}}
.cursor-glow{position:fixed;left:-400px;top:-400px;width:340px;height:340px;border-radius:50%;pointer-events:none;z-index:0;background:radial-gradient(circle,color-mix(in srgb,var(--purple) 30%,transparent),transparent 65%);transform:translate(-50%,-50%);transition:left .15s ease-out,top .15s ease-out}
.ripple{position:absolute;border-radius:50%;background:rgba(255,255,255,.5);transform:scale(0);animation:rip .6s ease-out;pointer-events:none}
@keyframes rip{to{transform:scale(4);opacity:0}}
.reveal{opacity:0;transform:translateY(40px) rotateX(18deg) scale(.96)}
.reveal.in{opacity:1;transform:none;transition:opacity .8s ease,transform .9s cubic-bezier(.2,.8,.2,1)}
@media (prefers-reduced-motion:reduce) {
  *,*::before,*::after { scroll-behavior:auto!important;animation:none!important;transition:none!important; }
}
</style>
</head>
<body>
<div class="fx-bg" aria-hidden="true">
  <div class="fx-blob b1"></div>
  <div class="fx-blob b2"></div>
  <div class="fx-blob b3"></div>
</div>
<div class="cursor-glow" id="cursorGlow" aria-hidden="true"></div>

<div class="app-container">
  <header class="wrap">
    <div class="brand">MY<span>SPACE</span> ✦</div>
    <nav aria-label="منوی سایت">
      <a href="#shop">خرید</a>
      <a href="#support">پشتیبانی</a>
      <button id="galleryBtn" class="icon-button" type="button" aria-label="انتخاب عکس پس‌زمینه" title="عکس گالری">🖼️</button>
      <button id="bgToggle" class="icon-button" type="button" aria-label="تغییر پالت رنگ" title="پالت رنگ">🎨</button>
      <button id="themeToggle" class="icon-button" type="button" aria-label="تغییر تم" title="تغییر تم">🌙</button>
      <button id="menuButton" class="icon-button" type="button" aria-label="باز کردن داشبورد" title="داشبورد">⋮</button>
    </nav>
  </header>

  <input type="file" id="wallpaperInput" accept="image/*" hidden>

  <div class="wrap">
    <div class="island-wrap">
      <div id="island" class="island" role="button" tabindex="0" aria-label="تغییر بین ساعت و تاریخ">
        <span id="islandIcon" class="island-icon">🕰️</span>
        <div>
          <div id="islandMain" class="island-main">--:--:--</div>
          <div id="islandSub" class="island-sub">ساعت محلی دستگاه</div>
        </div>
        <div class="island-dots"><span id="dot0" class="active"></span><span id="dot1"></span></div>
      </div>
    </div>
  </div>

  <main class="wrap">
    <section class="hero glass reveal">
      <div class="eyebrow">YOUR PERSONAL SPACE</div>
      <h1>به فضای <span class="gradient">شخصی من</span> خوش آمدی</h1>
      <p>محیط موبایلی شیشه‌ای با قابلیت انتخاب عکس گالری و تغییر رنگ.</p>
      <span class="tag">Mobile Dashboard · Dynamic Island · Glass</span>
    </section>

    <section id="shop" class="card glass product reveal">
      <div class="product-icon">✧</div>
      <span class="tag">محصول ویژه</span>
      <h2 style="margin-top:10px">خرید و دریافت</h2>
      <p>دسترسی به محصول دیجیتال</p>
      <div class="price">۹۹٬۰۰۰ تومان</div>
      <button id="buyButton" class="button" type="button">خرید محصول</button>
      <div id="buyStatus" class="status" role="status">پرداخت هنوز راه‌اندازی نشده است.</div>
    </section>

    <section class="card glass reveal">
      <h2>دربارهٔ سایت</h2>
      <p>وب‌سایت شخصی با افکت‌های شیشه‌ای، انتخاب عکس، تغییر پالت و تم روشن و تاریک.</p>
    </section>

    <section id="support" class="card glass support-card reveal">
      <div style="font-size:30px">💬</div>
      <h2>پشتیبانی و ارتباط با ما</h2>
      <p>سؤال یا پیشنهادی داری؟ در ارتباط باش.</p>
      <div class="support-links">
        <a class="button secondary" href="mailto:yeganehali019@gmail.com">✉️ ایمیل پشتیبانی</a>
        <a class="button secondary" href="mailto:yeganehali019@gmail.com?subject=Suggestion%20%2F%20Bug%20Report">💡 پیشنهاد / گزارش باگ</a>
      </div>
    </section>
  </main>

  <footer class="wrap">
    <div>ساخته شده با ✦ توسط <span class="footer-name">علی</span></div>
    <div>© 2026 · تمامی حقوق محفوظ است</div>
  </footer>
</div>

<div id="dashboardOverlay" class="overlay" hidden>
  <div id="overlayBackdrop" class="overlay-backdrop"></div>
  <section class="overlay-panel glass" role="dialog" aria-modal="true" aria-labelledby="dialogTitle">
    <button id="closeDashboard" class="overlay-close" type="button" aria-label="بستن داشبورد">✕</button>

    <div id="loginBox">
      <h2 id="dialogTitle">حساب کاربری</h2>
      <p>برای ورود یا ساخت حساب، اطلاعاتت را وارد کن.</p>
      <button id="googleButton" class="button secondary full" type="button">🌐 ورود با گوگل (دمو)</button>
      <form id="emailForm">
        <label for="email">ایمیل</label>
        <input id="email" type="email" autocomplete="email" placeholder="name@example.com" required>
        <label for="password">رمز عبور</label>
        <input id="password" type="password" minlength="6" autocomplete="current-password" placeholder="حداقل ۶ نویسه" required>
        <button id="signupButton" class="button full" type="submit">ساخت حساب</button>
        <button id="loginButton" class="button secondary full" type="button">ورود به حساب</button>
        <button id="resetButton" class="button secondary full" type="button">فراموشی رمز عبور</button>
      </form>
      <div id="accountStatus" class="status" role="status" aria-live="polite"></div>
    </div>

    <div id="dashboardBox" hidden>
      <h2>داشبورد من</h2>
      <div class="dash-grid">
        <div class="dash-card dash-profile">
          <div class="dash-avatar">👤</div>
          <div style="min-width:0">
            <div id="dashName" class="dash-value">کاربر</div>
            <div id="dashEmail" style="font-size:12px;color:var(--muted);overflow-wrap:anywhere">—</div>
            <div id="dashUid" class="dash-id">—</div>
          </div>
        </div>
        <div class="dash-card">
          <div class="dash-label">وضعیت ایمیل</div>
          <div id="dashVerifiedBadge" class="dash-value">—</div>
        </div>
        <div class="dash-card">
          <div class="dash-label">تاریخ عضویت</div>
          <div id="dashCreated" class="dash-value">—</div>
        </div>
        <div class="dash-card">
          <div class="dash-label">آخرین ورود</div>
          <div id="dashLastLogin" class="dash-value">—</div>
        </div>
      </div>
      <div class="dash-actions">
        <button id="logoutButton" class="button secondary" type="button">خروج</button>
      </div>
    </div>
  </section>
</div>

<script>
(function () {
  'use strict';

  // ---------- Helpers ----------
  const $ = (sel, root = document) => root.querySelector(sel);
  const $$ = (sel, root = document) => [...root.querySelectorAll(sel)];

  function pad(n) { return String(n).padStart(2, '0'); }

  function formatTime(d) {
    return `${pad(d.getHours())}:${pad(d.getMinutes())}:${pad(d.getSeconds())}`;
  }

  function formatDate(d) {
    try {
      return new Intl.DateTimeFormat('fa-IR', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' }).format(d);
    } catch {
      return d.toLocaleDateString('fa-IR');
    }
  }

  function toast(el, msg, ms = 2500) {
    if (!el) return;
    el.textContent = msg;
    clearTimeout(el._t);
    el._t = setTimeout(() => { el.textContent = el.dataset.default || ''; }, ms);
  }

  // ---------- Theme ----------
  const themeToggle = $('#themeToggle');
  const root = document.documentElement;

  function applyTheme(theme) {
    if (theme === 'light') {
      root.setAttribute('data-theme', 'light');
      themeToggle.textContent = '☀️';
      document.querySelector('meta[name="theme-color"]').content = '#f1f5f9';
    } else {
      root.removeAttribute('data-theme');
      themeToggle.textContent = '🌙';
      document.querySelector('meta[name="theme-color"]').content