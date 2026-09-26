<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Lukas Misyunas — Python Developer</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
      color: #fff;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 40px 20px;
    }
    .card {
      max-width: 800px;
      width: 100%;
      background: rgba(255,255,255,0.05);
      backdrop-filter: blur(20px);
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: 24px;
      padding: 48px;
      text-align: center;
      box-shadow: 0 20px 60px rgba(0,0,0,0.5);
    }
    h1 {
      font-size: 42px;
      margin-bottom: 12px;
      background: linear-gradient(90deg, #2E9EF7, #6A11CB);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .subtitle {
      font-size: 18px;
      color: #9aa4b2;
      margin-bottom: 32px;
    }
    .links {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
      margin-bottom: 40px;
    }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 12px 24px;
      border-radius: 12px;
      text-decoration: none;
      color: #fff;
      font-weight: 600;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .btn:hover { transform: translateY(-3px); box-shadow: 0 10px 25px rgba(0,0,0,0.4); }
    .btn-tg { background: #2CA5E0; }
    .btn-mail { background: #D14836; }
    .section {
      text-align: left;
      margin-bottom: 32px;
    }
    .section h2 {
      font-size: 22px;
      margin-bottom: 16px;
      color: #2E9EF7;
    }
    ul { list-style: none; }
    ul li {
      padding: 8px 0 8px 24px;
      position: relative;
      color: #c9d1d9;
    }
    ul li::before {
      content: "▸";
      position: absolute;
      left: 0;
      color: #6A11CB;
    }
    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }
    .tag {
      background: rgba(46,158,247,0.15);
      border: 1px solid rgba(46,158,247,0.4);
      color: #6ec1ff;
      padding: 6px 14px;
      border-radius: 20px;
      font-size: 14px;
    }
    .footer {
      margin-top: 32px;
      padding-top: 24px;
      border-top: 1px solid rgba(255,255,255,0.1);
      color: #6e7681;
      font-size: 14px;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Lukas Misyunas</h1>
    <p class="subtitle">Python Developer · Future ML Engineer · 13 y.o.</p>

    <div class="links">
      <a class="btn btn-tg" href="https://t.me/LMDigital1" target="_blank">✈️ Telegram</a>
      <a class="btn btn-mail" href="mailto:lukas.misyunas@gmail.com">✉️ Email</a>
    </div>

    <div class="section">
      <h2>👋 About Me</h2>
      <ul>
        <li>🔭 Работаю над backend-проектами на Python</li>
        <li>🌱 Изучаю Machine Learning и FastAPI</li>
        <li>🎯 Цель: стать ML-инженером</li>
      </ul>
    </div>

    <div class="section">
      <h2>🛠️ Tech Stack</h2>
      <div class="tags">
        <span class="tag">Python</span>
        <span class="tag">Git</span>
        <span class="tag">GitHub</span>
        <span class="tag">Linux</span>
        <span class="tag">SQL</span>
        <span class="tag">FastAPI</span>
        <span class="tag">NumPy</span>
        <span class="tag">Pandas</span>
      </div>
    </div>

    <div class="section">
      <h2>📚 Currently Learning</h2>
      <div class="tags">
        <span class="tag">Machine Learning</span>
        <span class="tag">PyTorch</span>
        <span class="tag">Docker</span>
      </div>
    </div>

    <div class="footer">
      ⭐️ Keep coding, keep growing!
    </div>
  </div>
</body>
</html>
