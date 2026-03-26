<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover, user-scalable=yes">
  <title>Angel | Биография — фриланс, код, путешествия</title>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      font-family: 'Inter', sans-serif;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1.2rem;
      position: relative;
      background: #0a0a1a;
    }

    /* АНИМИРОВАННЫЙ ФОН — фиолетово-бело-черный градиент */
    .animated-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
      background: linear-gradient(125deg, #1a0b2e 0%, #2d1b3c 25%, #3c2a4f 50%, #221b35 75%, #0f0a1f 100%);
      background-size: 400% 400%;
      animation: gradientShift 12s ease infinite;
    }

    .animated-bg::before {
      content: '';
      position: absolute;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 40%, rgba(180, 130, 255, 0.15) 0%, rgba(0, 0, 0, 0.4) 100%);
      pointer-events: none;
    }

    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .floating-particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      pointer-events: none;
      overflow: hidden;
    }

    .particle {
      position: absolute;
      background: rgba(210, 170, 255, 0.35);
      border-radius: 50%;
      filter: blur(40px);
      animation: floatParticle 18s infinite ease-in-out;
    }

    @keyframes floatParticle {
      0% { transform: translateY(0px) translateX(0px) scale(1); opacity: 0.3; }
      50% { transform: translateY(-40px) translateX(30px) scale(1.2); opacity: 0.6; }
      100% { transform: translateY(0px) translateX(0px) scale(1); opacity: 0.3; }
    }

    /* главная карточка */
    .bio-card {
      max-width: 580px;
      width: 100%;
      margin: 0 auto;
      background: rgba(15, 12, 25, 0.85);
      backdrop-filter: blur(12px);
      border-radius: 2.5rem;
      box-shadow: 0 30px 45px rgba(0, 0, 0, 0.5), 0 0 0 1px rgba(210, 170, 255, 0.25);
      overflow: hidden;
      transition: transform 0.25s ease, box-shadow 0.3s;
      border: 1px solid rgba(200, 160, 255, 0.3);
    }

    .bio-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 35px 55px rgba(0, 0, 0, 0.6);
      border-color: rgba(200, 160, 255, 0.6);
    }

    /* шапка профиля */
    .hero {
      background: linear-gradient(115deg, #170e2a 0%, #21153b 100%);
      padding: 2rem 1.5rem 2rem 1.5rem;
      text-align: center;
      border-bottom: 1px solid rgba(210, 170, 255, 0.3);
    }

    .avatar-icon {
      background: linear-gradient(145deg, #2a1b44, #19112f);
      width: 100px;
      height: 100px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 1rem;
      border-radius: 50%;
      border: 3px solid #c9adff;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4), 0 0 12px rgba(170, 120, 255, 0.4);
    }

    .avatar-icon i {
      font-size: 3.8rem;
      color: #e5d5ff;
      filter: drop-shadow(0 2px 5px rgba(0,0,0,0.3));
    }

    .hero h1 {
      font-family: 'Space Grotesk', monospace;
      font-size: 2.8rem;
      font-weight: 700;
      background: linear-gradient(135deg, #ffffff, #d9bbff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.5px;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(210, 170, 255, 0.2);
      backdrop-filter: blur(4px);
      padding: 0.4rem 1.2rem;
      border-radius: 60px;
      font-size: 0.8rem;
      font-weight: 500;
      margin-top: 0.7rem;
      color: #e2d0ff;
      border: 1px solid rgba(210, 170, 255, 0.4);
    }

    /* контент */
    .content {
      padding: 1.6rem 1.4rem 1.8rem;
    }

    /* информация сетка */
    .info-grid {
      display: flex;
      flex-direction: column;
      gap: 0.9rem;
      margin-bottom: 1.6rem;
    }

    .info-row {
      background: rgba(10, 8, 20, 0.7);
      border-radius: 1.5rem;
      padding: 0.8rem 1.2rem;
      display: flex;
      align-items: center;
      gap: 1rem;
      border: 1px solid rgba(210, 170, 255, 0.2);
      backdrop-filter: blur(4px);
    }

    .info-icon {
      width: 44px;
      height: 44px;
      background: #241d38;
      border-radius: 30px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.4rem;
      color: #cfb5ff;
    }

    .info-text {
      flex: 1;
    }

    .info-label {
      font-size: 0.7rem;
      text-transform: uppercase;
      font-weight: 600;
      letter-spacing: 1px;
      color: #b59eff;
    }

    .info-value {
      font-size: 1.1rem;
      font-weight: 600;
      color: #f2edff;
      word-break: break-word;
      display: flex;
      align-items: center;
      gap: 6px;
      flex-wrap: wrap;
    }

    /* секции */
    .section-card {
      background: rgba(0, 0, 0, 0.45);
      backdrop-filter: blur(8px);
      border-radius: 1.6rem;
      padding: 1.2rem 1.2rem;
      margin-bottom: 1.4rem;
      border: 1px solid rgba(210, 170, 255, 0.25);
      transition: 0.2s;
    }

    .section-title {
      font-size: 1.3rem;
      font-weight: 700;
      font-family: 'Space Grotesk', monospace;
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 0.9rem;
      color: #e2ceff;
      border-left: 4px solid #bc9aff;
      padding-left: 12px;
    }

    .about-text {
      font-size: 0.92rem;
      line-height: 1.5;
      color: #ded9f0;
    }

    /* теги интересов */
    .interests-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-top: 0.5rem;
    }

    .interest-tag {
      background: rgba(50, 35, 85, 0.7);
      padding: 0.4rem 1rem;
      border-radius: 40px;
      font-size: 0.75rem;
      font-weight: 500;
      color: #e0ceff;
      display: inline-flex;
      align-items: center;
      gap: 7px;
      border: 1px solid rgba(210, 170, 255, 0.3);
    }

    /* ссылки Telegram */
    .tg-link-list {
      display: flex;
      flex-direction: column;
      gap: 0.75rem;
      margin-top: 0.5rem;
    }

    .tg-link-item {
      background: rgba(35, 25, 65, 0.7);
      border-radius: 1.2rem;
      padding: 0.7rem 1rem;
      display: flex;
      align-items: center;
      gap: 12px;
      text-decoration: none;
      transition: all 0.2s;
      border: 1px solid rgba(210, 170, 255, 0.3);
    }

    .tg-link-item i {
      font-size: 1.6rem;
      color: #bc9aff;
      width: 32px;
      text-align: center;
    }

    .tg-link-info {
      flex: 1;
    }

    .tg-link-name {
      font-weight: 700;
      color: #ffffff;
      font-size: 0.95rem;
      letter-spacing: -0.2px;
    }

    .tg-link-desc {
      font-size: 0.7rem;
      color: #bc9eff;
      font-family: monospace;
    }

    .tg-link-item:hover {
      background: #2f2352;
      border-color: #bc9aff;
      transform: translateX(6px);
    }

    /* друзья */
    .friends-wrap {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem;
      margin-top: 0.5rem;
    }

    .friend-badge {
      background: rgba(0, 0, 0, 0.5);
      padding: 0.4rem 1rem;
      border-radius: 40px;
      font-size: 0.85rem;
      font-weight: 500;
      color: #dbcaff;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border: 1px solid #6d4f9e;
      text-decoration: none;
      transition: 0.2s;
    }

    .friend-badge:hover {
      background: #2f2352;
      border-color: #bc9aff;
      transform: scale(1.02);
    }

    .friend-badge i {
      font-size: 0.8rem;
      color: #bc9aff;
    }

    /* анонимная кнопка */
    .anon-button {
      background: linear-gradient(135deg, #2f2352, #1e1738);
      border-radius: 1.2rem;
      padding: 0.9rem 1rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      text-decoration: none;
      transition: all 0.2s;
      border: 1px solid rgba(210, 170, 255, 0.4);
      margin-bottom: 1.4rem;
    }

    .anon-button:hover {
      background: #3e2e6b;
      transform: translateX(5px);
      border-color: #bc9aff;
    }

    .anon-left {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .anon-left i {
      font-size: 1.8rem;
      color: #bc9aff;
    }

    .anon-text {
      color: #ffffff;
      font-weight: 600;
      font-size: 0.95rem;
    }

    .anon-sub {
      font-size: 0.7rem;
      color: #bc9eff;
      margin-top: 2px;
    }

    .anon-arrow {
      color: #bc9aff;
      font-size: 1.2rem;
    }

    /* футер */
    .footer-note {
      text-align: center;
      font-size: 0.7rem;
      color: #9f8bc2;
      margin-top: 1.2rem;
      padding-top: 0.8rem;
      border-top: 1px solid rgba(210, 170, 255, 0.2);
    }

    .link-tg {
      color: #bc9aff;
      text-decoration: none;
      font-weight: 500;
    }

    .link-tg:hover {
      text-decoration: underline;
      color: white;
    }

    /* адаптация под телефоны */
    @media (max-width: 550px) {
      body {
        padding: 0.9rem;
      }
      .hero h1 {
        font-size: 2.2rem;
      }
      .avatar-icon {
        width: 85px;
        height: 85px;
      }
      .avatar-icon i {
        font-size: 3rem;
      }
      .content {
        padding: 1.2rem;
      }
      .info-value {
        font-size: 0.95rem;
      }
      .section-title {
        font-size: 1.2rem;
      }
    }
  </style>
</head>
<body>
  <!-- анимированный фон -->
  <div class="animated-bg"></div>
  <div class="floating-particles">
    <div class="particle" style="width: 250px; height: 250px; top: 10%; left: -5%; animation-duration: 20s;"></div>
    <div class="particle" style="width: 180px; height: 180px; bottom: 15%; right: -3%; animation-duration: 25s;"></div>
    <div class="particle" style="width: 300px; height: 300px; top: 40%; right: 20%; animation-duration: 22s; opacity: 0.2;"></div>
  </div>

  <div class="bio-card">
    <div class="hero">
      <div class="avatar-icon">
        <i class="fas fa-laptop-code"></i>
      </div>
      <h1>Angel</h1>
      <div class="hero-tag">
        <i class="fas fa-code"></i> 15 лет · Армения <i class="fas fa-heart" style="color:#ff99cc;"></i>
      </div>
    </div>

    <div class="content">
      <!-- основная информация: возраст, национальность, пол -->
      <div class="info-grid">
        <div class="info-row">
          <div class="info-icon"><i class="fas fa-mars"></i></div>
          <div class="info-text">
            <div class="info-label">Пол</div>
            <div class="info-value">Парень</div>
          </div>
        </div>
        <div class="info-row">
          <div class="info-icon"><i class="fas fa-birthday-cake"></i></div>
          <div class="info-text">
            <div class="info-label">Возраст</div>
            <div class="info-value">15 лет</div>
          </div>
        </div>
        <div class="info-row">
          <div class="info-icon"><i class="fas fa-flag"></i></div>
          <div class="info-text">
            <div class="info-label">Национальность / Родина</div>
            <div class="info-value">
              <img src="https://flagcdn.com/w40/am.png" alt="Armenia flag" style="width: 22px; height: 16px; border-radius: 2px; margin-right: 4px;">
              Армения · Армянский дух 🇦🇲
            </div>
          </div>
        </div>
        <div class="info-row">
          <div class="info-icon"><i class="fab fa-telegram"></i></div>
          <div class="info-text">
            <div class="info-label">Telegram (личный)</div>
            <div class="info-value">
              <a href="https://t.me/Angelchik8" target="_blank" class="link-tg">@Angelchik8</a>
              <i class="fas fa-external-link-alt" style="font-size: 0.7rem; opacity: 0.7;"></i>
            </div>
          </div>
        </div>
      </div>

      <!-- О себе: фриланс, заработок, программирование -->
      <div class="section-card">
        <div class="section-title">
          <i class="fas fa-user-astronaut"></i> 
          <span>👋 Привет, я Angel</span>
        </div>
        <div class="about-text">
          Мне 15 лет, я из Армении 🇦🇲. Интересуюсь <strong>заработком в интернете, фрилансом и программированием</strong>. 
          Создаю сайты, занимаюсь frontend-разработкой, изучаю современные технологии. Фриланс — это свобода и возможность 
          реализовывать крутые проекты. Постоянно развиваюсь в IT-сфере, люблю решать задачи и прокачивать скиллы.
          <br><br>
          Веду Telegram-каналы, где делюсь полезной информацией про заработок, путешествия и инструменты для работы.
        </div>
      </div>

      <!-- Telegram каналы -->
      <div class="section-card">
        <div class="section-title">
          <i class="fab fa-telegram-plane"></i>
          <span>📢 мои Telegram-каналы</span>
        </div>
        <div class="tg-link-list">
          <a href="https://t.me/apxfw8" target="_blank" class="tg-link-item">
            <i class="fab fa-telegram"></i>
            <div class="tg-link-info">
              <div class="tg-link-name">@apxfw8</div>
              <div class="tg-link-desc">💰 заработок в интернете · фриланс · советы</div>
            </div>
            <i class="fas fa-arrow-right" style="color:#bc9aff;"></i>
          </a>
          <a href="https://t.me/angelvpns" target="_blank" class="tg-link-item">
            <i class="fab fa-telegram"></i>
            <div class="tg-link-info">
              <div class="tg-link-name">@angelvpns</div>
              <div class="tg-link-desc">🔒 VPN, безопасность, технологии</div>
            </div>
            <i class="fas fa-arrow-right" style="color:#bc9aff;"></i>
          </a>
          <a href="https://t.me/angelholidays" target="_blank" class="tg-link-item">
            <i class="fab fa-telegram"></i>
            <div class="tg-link-info">
              <div class="tg-link-name">@angelholidays</div>
              <div class="tg-link-desc">✈️ страны, путешествия, вдохновение</div>
            </div>
            <i class="fas fa-arrow-right" style="color:#bc9aff;"></i>
          </a>
        </div>
      </div>

      <!-- Анонимные сообщения -->
      <a href="http://t.me/anonaskbot?start=us_fdshck" target="_blank" class="anon-button">
        <div class="anon-left">
          <i class="fas fa-comment-dots"></i>
          <div>
            <div class="anon-text">Анонимные сообщения</div>
            <div class="anon-sub">спросить что угодно / сказать анонимно</div>
          </div>
        </div>
        <div class="anon-arrow">
          <i class="fas fa-chevron-right"></i>
        </div>
      </a>

      <!-- Мои друзья -->
      <div class="section-card">
        <div class="section-title">
          <i class="fas fa-users"></i>
          <span>🤝 мои друзья</span>
        </div>
        <div class="friends-wrap">
          <a href="https://t.me/rcbr12" target="_blank" class="friend-badge">
            <i class="fab fa-telegram"></i> @rcbr12
          </a>
          <a href="https://t.me/Onellehko" target="_blank" class="friend-badge">
            <i class="fab fa-telegram"></i> @Onellehko
          </a>
          <a href="https://t.me/Xxxnnm16" target="_blank" class="friend-badge">
            <i class="fab fa-telegram"></i> @Xxxnnm16
          </a>
        </div>
      </div>

      <!-- Интересы: программирование, фриланс + ЛЮБОВЬ К ШВЕЙЦАРИИ и скандинавским странам -->
      <div class="section-card">
        <div class="section-title">
          <i class="fas fa-heart"></i>
          <span>🔥 мои интересы</span>
        </div>
        <div class="interests-list">
          <span class="interest-tag"><i class="fas fa-code"></i> Программирование</span>
          <span class="interest-tag"><i class="fas fa-chart-line"></i> Фриланс / заработок</span>
          <span class="interest-tag"><i class="fas fa-globe"></i> Веб-разработка</span>
          <span class="interest-tag"><i class="fas fa-mountain"></i> Швейцария ❤️</span>
          <span class="interest-tag"><i class="fas fa-plane"></i> Путешествия</span>
        </div>
        <div class="about-text" style="margin-top: 12px;">
          <i class="fas fa-heart" style="color:#ff99cc;"></i> <strong>Моя любовь — страны:</strong> 
          <span style="font-size: 1.2rem;">🇨🇭 🇸🇪 🇩🇰 🇳🇴</span> 
          — Швейцария, Швеция, Дания, Норвегия. Альпы, скандинавский стиль, порядок и качество жизни — моё вдохновение.
        </div>
        <div class="about-text" style="margin-top: 8px; font-size: 0.85rem; opacity: 0.8;">
          📌 <em>По работе — не актуально</em>
        </div>
      </div>

      <div class="footer-note">
        <i class="fas fa-laptop-code"></i> Angel · 15 лет · Армения | Фриланс, код, путешествия ♡
      </div>
    </div>
  </div>
</body>
</html>
