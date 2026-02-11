<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Brian — humble abode</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #050509;
      --card: #101018;
      --accent: #6b8bff;
      --accent-soft: rgba(107, 139, 255, 0.25);
      --text-main: #f5f5f7;
      --text-muted: #9b9bb2;
      --danger: #ff5c7a;
      --success: #4ade80;
      --grid-line: rgba(255, 255, 255, 0.04);
      --radius: 14px;
      --shadow-soft: 0 18px 45px rgba(0, 0, 0, 0.7);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: "Space Grotesk", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      background: radial-gradient(circle at top, #181827 0, #050509 55%);
      color: var(--text-main);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 32px;
    }

    .grid-bg {
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(var(--grid-line) 1px, transparent 1px),
        linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
      background-size: 40px 40px;
      opacity: 0.6;
      pointer-events: none;
      z-index: -2;
    }

    .glow {
      position: fixed;
      inset: 0;
      background:
        radial-gradient(circle at 20% 10%, rgba(107, 139, 255, 0.25), transparent 55%),
        radial-gradient(circle at 80% 80%, rgba(244, 114, 182, 0.18), transparent 55%);
      mix-blend-mode: screen;
      pointer-events: none;
      z-index: -1;
    }

    .shell {
      width: min(1100px, 100%);
      aspect-ratio: 16 / 9;
      border-radius: 24px;
      border: 1px solid rgba(255, 255, 255, 0.06);
      background: radial-gradient(circle at top left, rgba(255, 255, 255, 0.04), transparent 55%),
                  rgba(5, 5, 12, 0.96);
      box-shadow: var(--shadow-soft);
      padding: 20px 22px;
      display: grid;
      grid-template-rows: auto 1fr auto;
      gap: 14px;
      position: relative;
      overflow: hidden;
    }

    .shell::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(255, 255, 255, 0.08), transparent 40%);
      mix-blend-mode: soft-light;
      opacity: 0.4;
      pointer-events: none;
    }

    .top-row {
      display: grid;
      grid-template-columns: 1.1fr 1.1fr 0.9fr;
      gap: 12px;
      z-index: 1;
    }

    .card {
      background: radial-gradient(circle at top, rgba(255, 255, 255, 0.04), transparent 55%),
                  var(--card);
      border-radius: var(--radius);
      border: 1px solid rgba(255, 255, 255, 0.06);
      padding: 10px 12px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.6);
      position: relative;
      overflow: hidden;
    }

    .card::after {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(120deg, rgba(107, 139, 255, 0.16), transparent 55%);
      mix-blend-mode: soft-light;
      opacity: 0;
      transition: opacity 0.25s ease-out;
      pointer-events: none;
    }

    .card:hover::after {
      opacity: 1;
    }

    .card-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 6px;
      font-size: 11px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--text-muted);
    }

    .pill {
      padding: 2px 8px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.12);
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: var(--text-muted);
    }

    .card-body {
      font-size: 12px;
      color: var(--text-main);
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .card-body ul {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .card-body li {
      display: flex;
      align-items: center;
      gap: 6px;
      color: var(--text-muted);
    }

    .bullet {
      width: 4px;
      height: 4px;
      border-radius: 999px;
      background: var(--accent);
      flex-shrink: 0;
    }

    .tag-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 4px;
    }

    .tag {
      font-size: 10px;
      padding: 2px 7px;
      border-radius: 999px;
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid rgba(255, 255, 255, 0.08);
      color: var(--text-muted);
    }

    .status-dot {
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: var(--success);
      box-shadow: 0 0 12px rgba(74, 222, 128, 0.9);
      margin-right: 4px;
    }

    .online {
      display: inline-flex;
      align-items: center;
      gap: 4px;
      font-size: 11px;
      color: var(--text-muted);
    }

    .center-row {
      display: grid;
      grid-template-columns: 1.1fr 1.1fr 0.9fr;
      gap: 12px;
      z-index: 1;
    }

    .center-left,
    .center-right {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .center-main {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: visible;
    }

    .name-stack {
      position: relative;
      font-size: 52px;
      font-weight: 700;
      text-transform: lowercase;
      letter-spacing: 0.08em;
      line-height: 1;
    }

    .name-stack span {
      position: absolute;
      inset: 0;
      color: var(--text-main);
      text-shadow: 0 0 18px rgba(0, 0, 0, 0.9);
    }

    .name-stack span:nth-child(1) {
      transform: translate(-4px, -2px);
      color: rgba(107, 139, 255, 0.7);
      filter: blur(1px);
      opacity: 0.7;
    }

    .name-stack span:nth-child(2) {
      transform: translate(4px, 2px);
      color: rgba(244, 114, 182, 0.7);
      filter: blur(1px);
      opacity: 0.7;
    }

    .name-stack span:nth-child(3) {
      position: relative;
      transform: translate(0, 0);
    }

    .center-caption {
      position: absolute;
      bottom: -18px;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--text-muted);
    }

    .play-chip {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 5px 9px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.16);
      background: rgba(0, 0, 0, 0.4);
      font-size: 11px;
      cursor: pointer;
      transition: background 0.2s ease-out, transform 0.15s ease-out;
      width: fit-content;
    }

    .play-chip:hover {
      background: rgba(107, 139, 255, 0.18);
      transform: translateY(-1px);
    }

    .play-icon {
      width: 16px;
      height: 16px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.4);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 9px;
    }

    .stat-big {
      font-size: 26px;
      font-weight: 600;
    }

    .stat-sub {
      font-size: 11px;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.12em;
    }

    .emoji-pill {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 4px 9px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.16);
      font-size: 11px;
      color: var(--text-muted);
      background: rgba(0, 0, 0, 0.4);
      width: fit-content;
    }

    .emoji-pill span:first-child {
      font-size: 14px;
    }

    .bottom-row {
      display: grid;
      grid-template-columns: 1.1fr 1.1fr 0.9fr;
      gap: 12px;
      align-items: flex-end;
      z-index: 1;
      font-size: 11px;
      color: var(--text-muted);
    }

    .socials {
      display: flex;
      gap: 10px;
      text-transform: lowercase;
    }

    .socials a {
      color: var(--text-muted);
      text-decoration: none;
      border-bottom: 1px dashed rgba(255, 255, 255, 0.18);
      padding-bottom: 1px;
      font-size: 11px;
    }

    .build-tag {
      text-align: right;
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    .bottom-center-note {
      text-align: center;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    .bottom-center-note span {
      color: var(--accent);
    }

    @media (max-width: 900px) {
      body {
        padding: 16px;
      }
      .shell {
        aspect-ratio: auto;
        height: auto;
        grid-template-rows: auto auto auto auto;
      }
      .top-row,
      .center-row,
      .bottom-row {
        grid-template-columns: 1fr;
      }
      .center-main {
        margin: 10px 0 24px;
      }
      .name-stack {
        font-size: 40px;
      }
    }
  </style>
</head>
<body>
  <div class="grid-bg"></div>
  <div class="glow"></div>

  <main class="shell">
    <!-- Top row -->
    <section class="top-row">
      <article class="card">
        <div class="card-header">
          <span>books</span>
          <span class="pill">reading list</span>
        </div>
        <div class="card-body">
          <ul>
            <li><span class="bullet"></span><span>linear algebra done right — axler</span></li>
            <li><span class="bullet"></span><span>option volatility &amp; pricing — natenberg</span></li>
            <li><span class="bullet"></span><span>+ whatever breaks my brain next</span></li>
          </ul>
        </div>
      </article>

      <article class="card">
        <div class="card-header">
          <span>goals</span>
          <span class="pill">2026 grind</span>
        </div>
        <div class="card-body">
          <ul>
            <li><span class="bullet"></span><span>learn as much math as possible</span></li>
            <li><span class="bullet"></span><span>C++ demon + clean systems design</span></li>
            <li><span class="bullet"></span><span>6 pack + V taper (slowly)</span></li>
            <li><span class="bullet"></span><span>afford something fun & loud</span></li>
          </ul>
        </div>
      </article>

      <article class="card">
        <div class="card-header">
          <span>stats</span>
          <span class="pill">irl build</span>
        </div>
        <div class="card-body">
          <ul>
            <li><span class="bullet"></span><span>student @ GSU — CS</span></li>
            <li><span class="bullet"></span><span>dev-in-progress, loves overengineering</span></li>
            <li><span class="bullet"></span><span>terrible at leetcode (for now)</span></li>
          </ul>
        </div>
      </article>
    </section>

    <!-- Center row -->
    <section class="center-row">
      <div class="center-left">
        <article class="card">
          <div class="card-header">
            <span>wsg</span>
            <span class="pill">about</span>
          </div>
          <div class="card-body">
            <span>i really like math, clean code, and building things that actually matter.</span>
            <div class="tag-row">
              <span class="tag">logic enjoyer</span>
              <span class="tag">automation scripts</span>
              <span class="tag">arg maps</span>
            </div>
          </div>
        </article>

        <button class="play-chip">
          <div class="play-icon">▶</div>
          <span>click me</span>
        </button>

        <article class="card">
          <div class="card-header">
            <span>typing</span>
            <span class="pill">skill issue?</span>
          </div>
          <div class="card-body">
            <div class="stat-big">100+ wpm</div>
            <div class="stat-sub">monkeytype / late night debugging</div>
          </div>
        </article>
      </div>

      <div class="center-main">
        <div class="name-stack" aria-label="brian">
          <span>brian</span>
          <span>brian</span>
          <span>brian</span>
        </div>
        <div class="center-caption">yo scroll down (if this scrolled)</div>
      </div>

      <div class="center-right">
        <article class="card">
          <div class="card-header">
            <span>welcome to my humble abode</span>
            <span class="online"><span class="status-dot"></span>online</span>
          </div>
          <div class="card-body">
            <span>currently juggling CS, math, and way too many side ideas.</span>
          </div>
        </article>

        <article class="card">
          <div class="card-header">
            <span>energy</span>
            <span class="pill">lfg</span>
          </div>
          <div class="card-body">
            <div class="emoji-pill">
              <span>😮‍💨</span>
              <span>calorie deficit + long walks</span>
            </div>
            <span style="margin-top:6px;">10k steps, some code, repeat.</span>
          </div>
        </article>

        <article class="card">
          <div class="card-header">
            <span>rating</span>
            <span class="pill">vibes</span>
          </div>
          <div class="card-body">
            <div class="stat-big">68 &plusmn; 1</div>
            <div class="stat-sub">self-estimated chaos score</div>
          </div>
        </article>
      </div>
    </section>

    <!-- Bottom row -->
    <section class="bottom-row">
      <div>
        <div class="socials">
          <a href="#">linkedin</a>
          <a href="#">github</a>
          <a href="#">instagram</a>
        </div>
      </div>

      <div class="bottom-center-note">
        house music is <span>trash</span> (fight me)
      </div>

      <div class="build-tag">
        build 2026.02.10
      </div>
    </section>
  </main>
</body>
</html>
