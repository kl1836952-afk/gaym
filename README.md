<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>انزل الجيم بقا</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&family=Tajawal:wght@400;800;900&display=swap" rel="stylesheet">
<style>
  :root {
    --red: #e8001d;
    --dark-red: #9b0012;
    --black: #080808;
    --near-black: #111;
    --white: #f5f5f0;
    --gray: #2a2a2a;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Cairo', sans-serif;
    overflow-x: hidden;
    cursor: crosshair;
  }

  /* Animated noise texture */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.05'/%3E%3C/svg%3E");
    background-size: 200px;
    opacity: 0.04;
    pointer-events: none;
    z-index: 999;
    animation: grain 0.5s steps(1) infinite;
  }

  @keyframes grain {
    0%,100% { transform: translate(0,0); }
    10% { transform: translate(-2%,-3%); }
    20% { transform: translate(3%,1%); }
    30% { transform: translate(-1%,4%); }
    40% { transform: translate(2%,-2%); }
    50% { transform: translate(-3%,3%); }
    60% { transform: translate(1%,-1%); }
    70% { transform: translate(-2%,2%); }
    80% { transform: translate(3%,-3%); }
    90% { transform: translate(-1%,1%); }
  }

  /* Hero Section */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    padding: 2rem;
    text-align: center;
  }

  /* Diagonal red stripe */
  .hero::after {
    content: '';
    position: absolute;
    top: -10%;
    left: -20%;
    width: 60%;
    height: 130%;
    background: var(--red);
    transform: skewX(-15deg);
    opacity: 0.07;
    pointer-events: none;
  }

  .hero-bg-text {
    position: absolute;
    font-family: 'Tajawal', sans-serif;
    font-weight: 900;
    font-size: clamp(120px, 25vw, 320px);
    color: var(--red);
    opacity: 0.04;
    user-select: none;
    pointer-events: none;
    white-space: nowrap;
    animation: bgPulse 3s ease-in-out infinite;
    letter-spacing: -0.05em;
  }

  @keyframes bgPulse {
    0%, 100% { opacity: 0.04; transform: scale(1); }
    50% { opacity: 0.07; transform: scale(1.02); }
  }

  .badge {
    display: inline-block;
    background: var(--red);
    color: var(--white);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.2em;
    padding: 0.4rem 1.2rem;
    text-transform: uppercase;
    margin-bottom: 2rem;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 50%, calc(100% - 12px) 100%, 0 100%, 12px 50%);
    animation: fadeDown 0.6s ease both;
  }

  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .main-title {
    font-family: 'Tajawal', sans-serif;
    font-weight: 900;
    font-size: clamp(3rem, 12vw, 9rem);
    line-height: 1;
    position: relative;
    z-index: 2;
    animation: fadeUp 0.8s ease 0.2s both;
    letter-spacing: -0.02em;
  }

  .main-title .highlight {
    color: var(--red);
    display: inline-block;
    position: relative;
  }

  .main-title .highlight::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 6px;
    background: var(--red);
    transform: scaleX(0);
    animation: underline 0.6s ease 1.2s forwards;
  }

  @keyframes underline {
    to { transform: scaleX(1); }
  }

  .subtitle {
    font-size: clamp(1rem, 3vw, 1.6rem);
    color: #aaa;
    margin: 1.5rem 0 3rem;
    font-weight: 400;
    animation: fadeUp 0.8s ease 0.5s both;
    max-width: 600px;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* Message input area */
  .message-box {
    position: relative;
    z-index: 2;
    animation: fadeUp 0.8s ease 0.7s both;
    width: 100%;
    max-width: 700px;
  }

  .message-display {
    background: var(--near-black);
    border: 2px solid #222;
    border-radius: 0;
    padding: 2.5rem 3rem;
    min-height: 180px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }

  .message-display::before {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 4px;
    height: 100%;
    background: var(--red);
  }

  .message-display:hover {
    border-color: #333;
  }

  .message-text {
    font-family: 'Tajawal', sans-serif;
    font-size: clamp(1.8rem, 5vw, 3.2rem);
    font-weight: 900;
    line-height: 1.3;
    color: var(--white);
    text-align: center;
    animation: textReveal 0.5s ease both;
    transition: all 0.3s;
  }

  @keyframes textReveal {
    from { opacity: 0; transform: scale(0.9); }
    to { opacity: 1; transform: scale(1); }
  }

  .message-text .accent {
    color: var(--red);
  }

  /* Shake animation for aggressive messages */
  @keyframes shake {
    0%, 100% { transform: translateX(0); }
    15% { transform: translateX(-8px) rotate(-1deg); }
    30% { transform: translateX(8px) rotate(1deg); }
    45% { transform: translateX(-6px); }
    60% { transform: translateX(6px); }
    75% { transform: translateX(-3px); }
    90% { transform: translateX(3px); }
  }

  .shake { animation: shake 0.6s ease both; }

  /* Controls */
  .controls {
    display: flex;
    gap: 1rem;
    margin-top: 1.5rem;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeUp 0.8s ease 0.9s both;
  }

  .btn {
    background: transparent;
    border: 2px solid var(--red);
    color: var(--red);
    padding: 1rem 2.5rem;
    font-family: 'Cairo', sans-serif;
    font-weight: 700;
    font-size: 1rem;
    cursor: pointer;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
    clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 50%, calc(100% - 10px) 100%, 0 100%, 10px 50%);
    letter-spacing: 0.05em;
  }

  .btn::before {
    content: '';
    position: absolute;
    inset: 0;
    background: var(--red);
    transform: scaleX(0);
    transform-origin: right;
    transition: transform 0.3s ease;
    z-index: -1;
  }

  .btn:hover::before { transform: scaleX(1); transform-origin: left; }
  .btn:hover { color: var(--white); }
  .btn:active { transform: scale(0.97); }

  .btn-primary {
    background: var(--red);
    color: var(--white);
  }

  .btn-primary::before { background: var(--dark-red); }

  /* Stats bar */
  .stats {
    display: flex;
    gap: 0;
    margin-top: 4rem;
    border: 1px solid #1e1e1e;
    animation: fadeUp 0.8s ease 1.1s both;
    width: 100%;
    max-width: 700px;
  }

  .stat {
    flex: 1;
    padding: 1.2rem;
    text-align: center;
    border-left: 1px solid #1e1e1e;
    position: relative;
    overflow: hidden;
  }

  .stat:last-child { border-left: none; }

  .stat::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: var(--red);
    transform: scaleX(0);
    transition: transform 0.4s ease;
  }

  .stat:hover::before { transform: scaleX(1); }

  .stat-num {
    font-family: 'Tajawal', sans-serif;
    font-size: 2rem;
    font-weight: 900;
    color: var(--red);
    display: block;
  }

  .stat-label {
    font-size: 0.75rem;
    color: #555;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin-top: 0.2rem;
    display: block;
  }

  /* Corner decoration */
  .corner {
    position: fixed;
    width: 60px;
    height: 60px;
    pointer-events: none;
    z-index: 100;
  }

  .corner-tl { top: 20px; right: 20px; border-top: 3px solid var(--red); border-right: 3px solid var(--red); }
  .corner-br { bottom: 20px; left: 20px; border-bottom: 3px solid var(--red); border-left: 3px solid var(--red); }

  /* Ticker */
  .ticker {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background: var(--red);
    padding: 0.6rem 0;
    overflow: hidden;
    z-index: 50;
  }

  .ticker-inner {
    display: flex;
    white-space: nowrap;
    animation: ticker 20s linear infinite;
  }

  .ticker-item {
    font-family: 'Tajawal', sans-serif;
    font-weight: 800;
    font-size: 0.85rem;
    letter-spacing: 0.15em;
    padding: 0 3rem;
    text-transform: uppercase;
  }

  .ticker-sep {
    opacity: 0.5;
    margin: 0 0.5rem;
  }

  @keyframes ticker {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  /* Progress ring */
  .ring-container {
    position: absolute;
    top: 2rem;
    left: 2rem;
    opacity: 0.15;
    animation: spin 20s linear infinite;
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  /* Pulse dot */
  .pulse-dot {
    width: 8px;
    height: 8px;
    background: var(--red);
    border-radius: 50%;
    display: inline-block;
    margin-left: 0.5rem;
    animation: pulse 1.5s ease infinite;
  }

  @keyframes pulse {
    0%, 100% { transform: scale(1); opacity: 1; }
    50% { transform: scale(1.8); opacity: 0.5; }
  }

  /* Screen flash */
  .flash {
    position: fixed;
    inset: 0;
    background: var(--red);
    z-index: 9999;
    pointer-events: none;
    opacity: 0;
    animation: flashAnim 0.4s ease both;
  }

  @keyframes flashAnim {
    0% { opacity: 0.3; }
    100% { opacity: 0; }
  }

  @media (max-width: 600px) {
    .stats { flex-direction: column; }
    .stat { border-left: none; border-top: 1px solid #1e1e1e; }
    .controls { gap: 0.7rem; }
    .btn { padding: 0.8rem 1.8rem; font-size: 0.9rem; }
    .message-display { padding: 2rem 1.5rem; }
  }
</style>
</head>
<body>

<div class="corner corner-tl"></div>
<div class="corner corner-br"></div>

<!-- Floating SVG ring -->
<div class="ring-container">
  <svg width="120" height="120" viewBox="0 0 120 120">
    <circle cx="60" cy="60" r="50" fill="none" stroke="#e8001d" stroke-width="1" stroke-dasharray="8 4"/>
    <circle cx="60" cy="60" r="35" fill="none" stroke="#e8001d" stroke-width="0.5" stroke-dasharray="4 8"/>
  </svg>
</div>

<section class="hero">
  <div class="hero-bg-text">جيم</div>

  <div class="badge">⚡ رسالة اليوم <span class="pulse-dot"></span></div>

  <h1 class="main-title">
    <span class="highlight">انزل</span><br>الجيم بقا
  </h1>

  <p class="subtitle">
    بعد إذنك… جسمك مش هيصبر لو انت صبرت 😤
  </p>

  <div class="message-box">
    <div class="message-display" id="msgDisplay">
      <p class="message-text" id="msgText">
        <span class="accent">يا عم الحاج</span> — انزل الجيم بقا يعجل! 💪
      </p>
    </div>

    <div class="controls">
      <button class="btn btn-primary" onclick="nextMessage()">🔥 رسالة جديدة</button>
      <button class="btn" onclick="escalate()">😤 عجلني أكتر!</button>
      <button class="btn" onclick="shareMsg()">📤 شاير</button>
    </div>
  </div>

  <div class="stats">
    <div class="stat">
      <span class="stat-num" id="counter">1</span>
      <span class="stat-label">رسائل بعتها</span>
    </div>
    <div class="stat">
      <span class="stat-num">0</span>
      <span class="stat-label">أعذار مقبولة</span>
    </div>
    <div class="stat">
      <span class="stat-num">∞</span>
      <span class="stat-label">كسل متبقي</span>
    </div>
  </div>
</section>

<!-- Ticker -->
<div class="ticker">
  <div class="ticker-inner" id="ticker">
    <span class="ticker-item">انزل الجيم <span class="ticker-sep">✦</span></span>
    <span class="ticker-item">وقفت تفكر في إيه بالظبط <span class="ticker-sep">✦</span></span>
    <span class="ticker-item">الكسل مش هيبني جسم <span class="ticker-sep">✦</span></span>
    <span class="ticker-item">ابدأ دلوقتي <span class="ticker-sep">✦</span></span>
    <span class="ticker-item">انزل الجيم <span class="ticker-sep">✦</span></span>
    <span class="ticker-item">وقفت تفكر في إيه بالظبط <span class="ticker-sep">✦</span></span>
    <span class="ticker-item">الكسل مش هيبني جسم <span class="ticker-sep">✦</span></span>
    <span class="ticker-item">ابدأ دلوقتي <span class="ticker-sep">✦</span></span>
  </div>
</div>

<script>
const messages = [
  { text: '💀 أنت لسه قاعد؟ الدمبلز بتعييط عليك!', level: 1 },
  { text: '🛋️ الكنبة مش عضلات يا صاحبي… قوم بقا!', level: 1 },
  { text: '⏰ كل دقيقة بتعدي من غير جيم دي خسارة!', level: 2 },
  { text: '🔥 الناس في الجيم دلوقتي وأنت هنا بتقرا؟!', level: 2 },
  { text: '😤 الجيم مش هيجيلك على البيت — قوم يا راجل!', level: 2 },
  { text: '💪 جسمك بيصرخ: "إمتى يا أخي إمتى?!"', level: 3 },
  { text: '🏋️ ما تنزلش الجيم ما تنزلش — بس لو عندك عذر قولي!', level: 3 },
  { text: '😡 أنت بتستنى إيه بالظبط؟ معجزة من السما؟!', level: 3 },
  { text: '🚨 تحذير: مستوى الكسل وصل الأحمر! انزل فوراً!', level: 3 },
  { text: '👊 لو مش رايح الجيم دلوقتي — أنا مش صاحبك!', level: 3 },
  { text: '🦁 السبت مش يوم راحة — السبت يوم الـ Chest Day!', level: 2 },
  { text: '📱 إنت بتسكرول وجسمك بيتفتت — انزل!', level: 1 },
  { text: '🎯 هدف بدون جيم = كلام فاضي يا فندم', level: 2 },
  { text: '💥 YALLA HABIBI — الجيم بيناديك من دلوقتي!', level: 3 },
  { text: '🥗 الأكل الصح + صفر جيم = مفيش نتيجة. قوم!', level: 1 },
];

const escalatedMessages = [
  { text: '🚨🚨 يا رجل!! جسمك بيطلب مساعدة دلوقتي!!', level: 3 },
  { text: '😤😤 اللي بيقرا ده ويمشيش للجيم — مش طبيعي!!', level: 3 },
  { text: '🔴 خطر شديد: كسل في المرحلة الأخيرة!! انزل!!', level: 3 },
  { text: '💣💣 الجيم ولا الندم — إنت بتختار دلوقتي!!', level: 3 },
  { text: '🆘 طوارئ لياقة! انزل الجيم فوراً يا معلم!!', level: 3 },
];

let count = 1;
let msgIndex = 0;

function flashScreen() {
  const f = document.createElement('div');
  f.className = 'flash';
  document.body.appendChild(f);
  setTimeout(() => f.remove(), 500);
}

function setMessage(msg) {
  const el = document.getElementById('msgText');
  const display = document.getElementById('msgDisplay');
  el.style.opacity = 0;
  el.style.transform = 'scale(0.85)';
  setTimeout(() => {
    el.innerHTML = msg.text;
    el.style.transition = 'all 0.4s cubic-bezier(0.34,1.56,0.64,1)';
    el.style.opacity = 1;
    el.style.transform = 'scale(1)';
    if (msg.level === 3) {
      el.style.color = '#ff2a2a';
      el.classList.add('shake');
      setTimeout(() => el.classList.remove('shake'), 700);
      flashScreen();
    } else {
      el.style.color = '#f5f5f0';
    }
  }, 250);
}

function nextMessage() {
  msgIndex = (msgIndex + 1) % messages.length;
  setMessage(messages[msgIndex]);
  count++;
  document.getElementById('counter').textContent = count;
}

function escalate() {
  const msg = escalatedMessages[Math.floor(Math.random() * escalatedMessages.length)];
  setMessage(msg);
  count++;
  document.getElementById('counter').textContent = count;
  // Shake the whole page slightly
  document.body.style.transform = 'translateX(4px)';
  setTimeout(() => {
    document.body.style.transform = 'translateX(-4px)';
    setTimeout(() => {
      document.body.style.transform = 'translateX(0)';
    }, 80);
  }, 80);
}

function shareMsg() {
  const text = document.getElementById('msgText').innerText;
  if (navigator.share) {
    navigator.share({ title: 'انزل الجيم بقا!', text: text, url: window.location.href });
  } else if (navigator.clipboard) {
    navigator.clipboard.writeText(text);
    const btn = document.querySelector('.btn:last-child');
    btn.textContent = '✅ اتنسخ!';
    setTimeout(() => btn.textContent = '📤 شاير', 2000);
  }
}

// Auto-cycle messages every 8 seconds
setInterval(nextMessage, 8000);
</script>
</body>
</html>
