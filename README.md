<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Yusuf Ertek - Profil</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-main: #141413;
      --bg-card: #1e1e1c;
      --bg-card-hover: #262624;
      --bg-pill: #252523;
      --border-subtle: rgba(255, 255, 255, 0.06);
      --text-primary: #f2f2f0;
      --text-secondary: #8e8d8a;
      --accent-coral: #e0533c;
      --accent-orange: #d97736;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-main);
      color: var(--text-primary);
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 24px;
    }

    .bento-wrapper {
      width: 100%;
      max-width: 780px;
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    /* Üst Bar - Görseldeki Duyuru ve Sağ Pill Alanı */
    .top-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      flex-wrap: wrap;
    }

    .status-banner {
      background: linear-gradient(90deg, var(--accent-coral), #c8412b);
      color: #ffffff;
      padding: 10px 20px;
      border-radius: 999px;
      font-size: 0.85rem;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      text-decoration: none;
      box-shadow: 0 4px 20px rgba(224, 83, 60, 0.25);
      transition: transform 0.2s ease, opacity 0.2s ease;
    }

    .status-banner:hover {
      transform: translateY(-1px);
      opacity: 0.95;
    }

    .status-dot {
      width: 8px;
      height: 8px;
      background-color: #fff;
      border-radius: 50%;
      display: inline-block;
    }

    .profile-pill {
      background-color: var(--bg-card);
      border: 1px solid var(--border-subtle);
      padding: 8px 16px;
      border-radius: 999px;
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--text-primary);
    }

    .profile-pill span.sub {
      color: var(--text-secondary);
      font-weight: 400;
    }

    /* Orta Kısım - 2'li Bento Grid */
    .middle-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 16px;
    }

    @media (max-width: 640px) {
      .middle-grid {
        grid-template-columns: 1fr;
      }
    }

    .card {
      background-color: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: 22px;
      padding: 24px;
      position: relative;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      transition: border-color 0.2s ease;
    }

    .card:hover {
      border-color: rgba(255, 255, 255, 0.12);
    }

    .card-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 18px;
    }

    .card-title-group {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .card-title {
      font-size: 1.05rem;
      font-weight: 700;
      letter-spacing: -0.01em;
    }

    .badge {
      background-color: rgba(217, 119, 54, 0.16);
      color: var(--accent-orange);
      font-size: 0.72rem;
      font-weight: 600;
      padding: 4px 10px;
      border-radius: 999px;
    }

    /* Sosyal Medya Listesi (Sol Kart - Menü/Yemek Listesi Sade Anlayışı) */
    .social-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .social-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 14px;
      border-radius: 14px;
      background-color: var(--bg-pill);
      color: var(--text-primary);
      text-decoration: none;
      font-size: 0.88rem;
      font-weight: 500;
      transition: background-color 0.2s ease, transform 0.15s ease;
    }

    .social-item:hover {
      background-color: var(--bg-card-hover);
      transform: translateX(3px);
    }

    .social-left {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .social-icon {
      width: 18px;
      height: 18px;
      fill: var(--accent-orange);
      opacity: 0.9;
    }

    .social-handle {
      color: var(--text-secondary);
      font-size: 0.8rem;
      font-weight: 400;
    }

    .card-footer-note {
      margin-top: 18px;
      font-size: 0.75rem;
      color: var(--text-secondary);
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .card-footer-note strong {
      color: var(--text-primary);
    }

    /* Sağ Kart - LENG Hub Hızlı Yönlendirme */
    .hub-card {
      background: radial-gradient(circle at top right, rgba(224, 83, 60, 0.14), transparent 65%), var(--bg-card);
      text-decoration: none;
      color: var(--text-primary);
      cursor: pointer;
    }

    .arrow-circle {
      width: 34px;
      height: 34px;
      border-radius: 50%;
      background-color: rgba(255, 255, 255, 0.06);
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background-color 0.2s ease, transform 0.2s ease;
    }

    .hub-card:hover .arrow-circle {
      background-color: var(--accent-coral);
      transform: translate(2px, -2px);
    }

    .hub-center {
      my: auto;
      padding: 16px 0;
    }

    .hub-label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      color: var(--text-secondary);
      margin-bottom: 6px;
    }

    .hub-domain {
      font-size: 1.55rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      color: #ffffff;
    }

    .hub-desc {
      font-size: 0.83rem;
      color: var(--text-secondary);
      margin-top: 8px;
      line-height: 1.45;
    }

    /* Alt Geniş Banner Kartı - Görseldeki "İHAMER Çalışmaları" Kart Yapısı */
    .showcase-banner {
      background: linear-gradient(180deg, rgba(20, 20, 19, 0.15) 0%, rgba(20, 20, 19, 0.92) 100%),
                  radial-gradient(circle at 20% 20%, #2e3532 0%, #1a1a18 100%);
      border: 1px solid var(--border-subtle);
      border-radius: 24px;
      padding: 32px 28px 26px 28px;
      min-height: 210px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      position: relative;
      text-decoration: none;
      color: var(--text-primary);
      overflow: hidden;
      transition: transform 0.2s ease, border-color 0.2s ease;
    }

    .showcase-banner:hover {
      border-color: rgba(224, 83, 60, 0.4);
      transform: translateY(-2px);
    }

    /* Arka planda minimal soyut ızgara dokusu */
    .showcase-banner::before {
      content: "";
      position: absolute;
      inset: 0;
      background-image: radial-gradient(rgba(255, 255, 255, 0.06) 1px, transparent 1px);
      background-size: 20px 20px;
      pointer-events: none;
    }

    .showcase-tag {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: #ffffff;
      margin-bottom: 8px;
      z-index: 1;
    }

    .showcase-tag span {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background-color: var(--accent-coral);
    }

    .showcase-title {
      font-size: 1.65rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      margin-bottom: 6px;
      z-index: 1;
    }

    .showcase-sub {
      font-size: 0.9rem;
      color: var(--text-secondary);
      max-width: 540px;
      z-index: 1;
    }

    /* Alt Nokta Göstergeleri (Görseldeki Slider Noktaları) */
    .dots-bar {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 6px;
      margin-top: 4px;
    }

    .dot {
      width: 6px;
      height: 6px;
      border-radius: 999px;
      background-color: #333330;
    }

    .dot.active {
      width: 22px;
      background-color: var(--accent-orange);
    }
  </style>
</head>
<body>

  <div class="bento-wrapper">
    
    <!-- Üst Satır: Kırmızı/Mercan Pill + Sağ Kullanıcı Pill -->
    <div class="top-bar">
      <a href="https://yusuf.leng.tr" target="_blank" class="status-banner">
        <span class="status-dot"></span>
        Tüm güncel projelerim ve bağlantılarım yusuf.leng.tr adresinde
      </a>

      <div class="profile-pill">
        <span>Yusuf Ertek</span>
        <span class="sub">• Computer Eng.</span>
      </div>
    </div>

    <!-- Orta Satır: 2'li Bento Kartları -->
    <div class="middle-grid">
      
      <!-- Sol Kart: Sosyal Medyalar -->
      <div class="card">
        <div>
          <div class="card-header">
            <div class="card-title-group">
              <span class="card-title">Sosyal Medya</span>
              <span class="badge">Bağlantılar</span>
            </div>
          </div>

          <div class="social-list">
            <a href="https://github.com/" target="_blank" class="social-item">
              <div class="social-left">
                <svg class="social-icon" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
                <span>GitHub</span>
              </div>
              <span class="social-handle">@yusufertek</span>
            </a>

            <a href="https://linkedin.com/" target="_blank" class="social-item">
              <div class="social-left">
                <svg class="social-icon" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
                <span>LinkedIn</span>
              </div>
              <span class="social-handle">in/yusufertek</span>
            </a>

            <a href="https://instagram.com/" target="_blank" class="social-item">
              <div class="social-left">
                <svg class="social-icon" viewBox="0 0 24 24"><path d="M7.8 2h8.4C19.4 2 22 4.6 22 7.8v8.4a5.8 5.8 0 0 1-5.8 5.8H7.8C4.6 22 2 19.4 2 16.2V7.8A5.8 5.8 0 0 1 7.8 2m-.2 2A3.6 3.6 0 0 0 4 7.6v8.8C4 18.39 5.61 20 7.6 20h8.8a3.6
