<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Be My Valentine Miss Ngwako? 💘</title>
  <style>
    :root{
      --bg1:#1a0012;
      --bg2:#2a0030;
      --pink:#ff4da6;
      --rose:#ff2e63;
      --soft:#ffd1e8;
      --card:#ffffff10;
      --card2:#ffffff18;
      --text:#fff;
    }

    *{ box-sizing:border-box; }
    body{
      margin:0;
      min-height:100vh;
      font-family: ui-rounded, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color:var(--text);
      overflow:hidden;
      background: radial-gradient(circle at 20% 10%, #ff2e6330, transparent 40%),
                  radial-gradient(circle at 80% 20%, #ff4da630, transparent 45%),
                  linear-gradient(135deg, var(--bg1), var(--bg2));
      display:flex;
      align-items:center;
      justify-content:center;
      padding:20px;
    }

    /* floating hearts */
    .hearts{
      position:fixed;
      inset:0;
      pointer-events:none;
      overflow:hidden;
      z-index:0;
    }
    .heart{
      position:absolute;
      bottom:-40px;
      font-size:18px;
      opacity:.85;
      animation: floatUp linear infinite;
      filter: drop-shadow(0 8px 18px #ff4da645);
    }
    @keyframes floatUp{
      from { transform: translateY(0) scale(1); opacity:0; }
      10% { opacity:.9; }
      to { transform: translateY(-120vh) scale(1.6); opacity:0; }
    }

    .card{
      position:relative;
      z-index:2;
      width:min(720px, 100%);
      background: linear-gradient(180deg, var(--card), var(--card2));
      border: 1px solid #ffffff20;
      border-radius:28px;
      padding:28px;
      box-shadow: 0 30px 90px #00000055;
      backdrop-filter: blur(10px);
    }

    .top{
      display:flex;
      gap:18px;
      align-items:center;
      justify-content:space-between;
      flex-wrap:wrap;
    }

    .badge{
      display:inline-flex;
      align-items:center;
      gap:10px;
      padding:10px 14px;
      border-radius:999px;
      background:#ffffff12;
      border:1px solid #ffffff1e;
      font-weight:600;
      letter-spacing:.2px;
    }

    h1{
      margin:14px 0 8px;
      font-size: clamp(34px, 4vw, 52px);
      line-height:1.05;
      letter-spacing:-0.5px;
    }

    .sub{
      margin:0;
      opacity:.92;
      font-size: clamp(15px, 2vw, 18px);
      line-height:1.5;
      color: var(--soft);
    }

    .quoteBox{
      margin-top:18px;
      padding:16px 18px;
      border-radius:18px;
      background:#ffffff0d;
      border:1px solid #ffffff1a;
      min-height:78px;
      display:flex;
      align-items:center;
      justify-content:center;
      text-align:center;
      font-size: clamp(15px, 2vw, 18px);
      line-height:1.5;
    }

    .quote{
      max-width: 60ch;
    }

    .actions{
      margin-top:22px;
      display:flex;
      gap:14px;
      justify-content:center;
      flex-wrap:wrap;
      position:relative;
      padding-bottom:6px;
    }

    button{
      border:none;
      cursor:pointer;
      font-weight:800;
      padding:14px 18px;
      border-radius:18px;
      font-size:16px;
      transition: transform .12s ease, box-shadow .12s ease;
      user-select:none;
    }

    .yes{
      background: linear-gradient(135deg, var(--rose), var(--pink));
      color:white;
      box-shadow: 0 16px 40px #ff2e6345;
    }
    .yes:hover{ transform: translateY(-2px) scale(1.02); }

    .no{
      background:#ffffff14;
      border:1px solid #ffffff22;
      color:#fff;
      box-shadow: 0 14px 35px #00000030;
      position:relative;
    }
    .no:hover{ transform: translateY(-2px); }

    .exit{
      background:#ffffff0f;
      border:1px solid #ffffff18;
      color:#ffd1e8;
      font-weight:700;
      padding:12px 14px;
      border-radius:16px;
    }

    .footer{
      margin-top:18px;
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:12px;
      flex-wrap:wrap;
      opacity:.9;
      font-size:13px;
      color:#ffd1e8c7;
    }

    .sparkle{
      display:inline-block;
      animation: sparkle 1.4s ease-in-out infinite;
    }
    @keyframes sparkle{
      0%,100%{ transform: translateY(0); }
      50%{ transform: translateY(-3px); }
    }

    .modal{
      position:fixed;
      inset:0;
      background:#00000070;
      display:none;
      align-items:center;
      justify-content:center;
      z-index:50;
      padding:18px;
    }
    .modal.open{ display:flex; }

    .modalCard{
      width:min(680px, 100%);
      background: linear-gradient(180deg, #ffffff18, #ffffff10);
      border: 1px solid #ffffff25;
      border-radius:28px;
      padding:26px;
      box-shadow: 0 40px 120px #00000070;
      backdrop-filter: blur(14px);
      text-align:center;
    }

    .modalCard h2{
      margin:0 0 10px;
      font-size: clamp(28px, 3vw, 40px);
    }
    .modalCard p{
      margin:0 auto;
      max-width:60ch;
      line-height:1.6;
      color:#ffe6f3;
      opacity:.95;
      font-size: 16px;
    }

    .bigHeart{
      font-size: 56px;
      margin: 10px 0 14px;
      filter: drop-shadow(0 16px 28px #ff4da660);
      animation: pulse 1.2s ease-in-out infinite;
    }
    @keyframes pulse{
      0%,100%{ transform: scale(1); }
      50%{ transform: scale(1.08); }
    }

    .close{
      margin-top:18px;
      background: linear-gradient(135deg, #ffffff1c, #ffffff10);
      border:1px solid #ffffff24;
      color:#fff;
      font-weight:800;
      padding:12px 16px;
      border-radius:16px;
    }

    /* Mobile safety: allow the "No" to move but not off-screen */
    @media (max-width: 520px){
      .actions{ gap:10px; }
      button{ width: 100%; }
      .no{ position:static; }
    }
  </style>
</head>
<body>
  <div class="hearts" id="hearts"></div>

  <main class="card">
    <div class="top">
      <div class="badge">💌 <span>Message from your least favorite person</span></div>
      <div class="badge">✨ <span class="sparkle">Made with love</span></div>
    </div>

    <h1>Pelontle, will you be my Valentine? 💘</h1>
    <p class="sub">
      Our situation may not be prefect, but I want to spend a day with <b>you</b>.
      And honestly… hopefully lot of days after that too. 🌙
    </p>

    <div class="quoteBox">
      <div class="quote" id="quote"></div>
    </div>

    <div class="actions" id="actions">
      <button class="yes" id="yesBtn">Yes 💖</button>
      <button class="no" id="noBtn">No??!! 🙈</button>
      <button class="exit" id="exitBtn">I need time - Heartbreak </button>
    </div>

    <div class="footer">
      <span>🌹 Romantic mode: <b>ON</b></span>
      <span>Tip: try clicking “No” 😌</span>
    </div>
  </main>

  <div class="modal" id="modal">
    <div class="modalCard">
      <div class="bigHeart">💗</div>
      <h2>You just made my whole heart smile.</h2>
      <p>
        Okay, listen… I’m officially the luckiest person alive.
        I promise to keep choosing you — gently, loudly, and always.  
        <br><br>
        Thank You For Choosing Me, My Valentine. 💘
      </p>
      <button class="close" id="closeBtn">Love YOU!!!</button>
    </div>
  </div>

  <script>
    const quotes = [
      "“If I had a flower for every time I thought of you… I could walk through my garden forever.” 🌸",
      "“I love you not only for what you are, but for what I am when I am with you.” 💞",
      "“You are my favorite notification.” 📲💗",
      "“Some people search their whole lives for this feeling.” ✨",
      "“You make all my problems disappear” 🏡💘",
      "“I don’t need a perfect love story… I just need you in mine.” 📖❤️",
      "“If kisses were stars, I’d give you the sky.” 🌙⭐",
      "“In a world full of maybe… you’re my yes and everything” 🥰",
      "“You + me = the softest kind of forever.” ♾️",
      "“I looked at you and thought: so this is what magic looks like.” ✨💗"
    ];

    const quoteEl = document.getElementById("quote");
    let idx = 0;

    function rotateQuote(){
      quoteEl.style.opacity = 0;
      setTimeout(() => {
        quoteEl.textContent = quotes[idx % quotes.length];
        idx++;
        quoteEl.style.opacity = 1;
      }, 180);
    }
    rotateQuote();
    setInterval(rotateQuote, 3800);

    // hearts
    const hearts = document.getElementById("hearts");
    const heartChars = ["💗","💖","💘","💕","💞","❤️","🌹","✨"];

    function spawnHeart(){
      const s = document.createElement("div");
      s.className = "heart";
      s.textContent = heartChars[Math.floor(Math.random()*heartChars.length)];
      s.style.left = Math.random() * 100 + "vw";
      s.style.fontSize = (14 + Math.random()*22) + "px";
      s.style.animationDuration = (5 + Math.random()*6) + "s";
      s.style.animationDelay = (Math.random()*0.8) + "s";
      hearts.appendChild(s);

      setTimeout(() => s.remove(), 12000);
    }
    setInterval(spawnHeart, 220);

    // modal
    const modal = document.getElementById("modal");
    document.getElementById("yesBtn").addEventListener("click", () => {
      modal.classList.add("open");
    });
    document.getElementById("closeBtn").addEventListener("click", () => {
      modal.classList.remove("open");
    });

    // playful "No" button that dodges (desktop/tablet)
    const noBtn = document.getElementById("noBtn");
    const actions = document.getElementById("actions");
    const exitBtn = document.getElementById("exitBtn");

    let noCount = 0;

    function moveNoButton(){
      noCount++;

      // after a few tries, soften it and respect boundaries
      if (noCount === 4) {
        noBtn.textContent = "I’m shy 😳";
      }
      if (noCount === 6) {
        noBtn.textContent = "Fine Maybe 😭";
      }
      if (noCount === 8) {
        noBtn.textContent = "You are hurting my feelings 🥺";
        }
      if (noCount === 10) {
        noBtn.textContent = "You're really picking NO?!";
          }
      if (noCount === 12) {
        noBtn.textContent = "Tjo, Tlogela geh - mxm";
      }

      const rect = actions.getBoundingClientRect();
      const btnRect = noBtn.getBoundingClientRect();

      // keep within actions container
      const maxX = rect.width + btnRect.width;
      const maxY = rect.height + btnRect.height;

      const x = Math.max(0, Math.random() * maxX);
      const y = Math.max(0, Math.random() * maxY);

      noBtn.style.position = "absolute";
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    }

    // dodge on hover AND on click
    noBtn.addEventListener("mouseenter", () => {
      if (window.innerWidth > 5) moveNoButton();
    });
    noBtn.addEventListener("click", () => {
      if (window.innerWidth > 5) moveNoButton();
    });

    // respectful exit option
    exitBtn.addEventListener("click", () => {
      quoteEl.textContent =
        "That’s okay, I understand. 💗 I like you a lot — and I respect you. If you ever want to talk, I’m here.";
      noBtn.style.position = "static";
      noBtn.textContent = "No 🙈";
    });

    // close modal by clicking outside
    modal.addEventListener("click", (e) => {
      if (e.target === modal) modal.classList.remove("open");
    });
  </script>
</body>
</html>
