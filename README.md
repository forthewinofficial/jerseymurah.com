<!DOCTYPE html>
<html lang="ms">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>JerseyKing – Jersey Murah Malaysia</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@400;600;700;900&family=Barlow+Condensed:wght@700;900&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --green: #00E676;
      --green-dark: #00C853;
      --black: #0A0A0A;
      --dark: #111111;
      --card: #161616;
      --text: #F0F0F0;
      --muted: #888;
      --red: #FF3B3B;
      --yellow: #FFD600;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--black);
      color: var(--text);
      font-family: 'Barlow', sans-serif;
      overflow-x: hidden;
    }

    /* ─── NAVBAR ─── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 16px 40px;
      background: rgba(10,10,10,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid #1f1f1f;
    }
    .logo {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 28px;
      letter-spacing: 2px;
      color: var(--green);
    }
    .logo span { color: var(--text); }
    nav ul { list-style: none; display: flex; gap: 32px; }
    nav ul li a {
      text-decoration: none; color: var(--muted);
      font-size: 14px; font-weight: 600; text-transform: uppercase;
      letter-spacing: 1px; transition: color 0.2s;
    }
    nav ul li a:hover { color: var(--green); }
    .nav-cta {
      background: var(--green); color: var(--black) !important;
      padding: 10px 22px; border-radius: 4px;
      font-weight: 700 !important; transition: background 0.2s !important;
    }
    .nav-cta:hover { background: var(--green-dark) !important; color: var(--black) !important; }

    /* ─── HERO ─── */
    .hero {
      min-height: 100vh;
      display: flex; align-items: center;
      position: relative; overflow: hidden;
      padding: 120px 40px 80px;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background:
        radial-gradient(ellipse 60% 60% at 70% 50%, rgba(0,230,118,0.08) 0%, transparent 70%),
        radial-gradient(ellipse 40% 40% at 20% 80%, rgba(0,200,83,0.05) 0%, transparent 60%);
    }
    .hero-grid {
      position: absolute; inset: 0; opacity: 0.04;
      background-image:
        linear-gradient(#00E676 1px, transparent 1px),
        linear-gradient(90deg, #00E676 1px, transparent 1px);
      background-size: 60px 60px;
    }
    .hero-content { position: relative; z-index: 1; max-width: 680px; }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: rgba(0,230,118,0.1); border: 1px solid rgba(0,230,118,0.3);
      color: var(--green); padding: 6px 16px; border-radius: 100px;
      font-size: 13px; font-weight: 700; letter-spacing: 1px;
      text-transform: uppercase; margin-bottom: 28px;
      animation: fadeUp 0.6s ease both;
    }
    .hero-badge::before { content: '⚡'; }
    .hero h1 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(64px, 9vw, 120px);
      line-height: 0.9;
      letter-spacing: 2px;
      animation: fadeUp 0.7s 0.1s ease both;
    }
    .hero h1 .highlight { color: var(--green); display: block; }
    .hero h1 .sub { color: var(--muted); font-size: 0.55em; display: block; letter-spacing: 4px; }
    .hero-desc {
      margin-top: 24px; font-size: 18px; color: #aaa; line-height: 1.7;
      max-width: 480px;
      animation: fadeUp 0.7s 0.2s ease both;
    }
    .hero-price-strip {
      margin-top: 36px; display: flex; gap: 12px; align-items: center;
      animation: fadeUp 0.7s 0.3s ease both;
    }
    .price-tag {
      background: var(--green); color: var(--black);
      font-family: 'Bebas Neue', sans-serif;
      font-size: 52px; padding: 8px 24px; border-radius: 4px;
      line-height: 1;
    }
    .price-info { display: flex; flex-direction: column; }
    .price-info .from { font-size: 12px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; }
    .price-info .orig { font-size: 22px; color: var(--muted); text-decoration: line-through; }
    .price-info .save { font-size: 13px; color: var(--red); font-weight: 700; }
    .hero-btns {
      margin-top: 36px; display: flex; gap: 16px; flex-wrap: wrap;
      animation: fadeUp 0.7s 0.4s ease both;
    }
    .btn-primary {
      background: var(--green); color: var(--black);
      padding: 16px 36px; border-radius: 4px; text-decoration: none;
      font-size: 16px; font-weight: 900; text-transform: uppercase;
      letter-spacing: 1px; transition: all 0.2s;
      border: none; cursor: pointer; display: inline-block;
    }
    .btn-primary:hover { background: var(--green-dark); transform: translateY(-2px); }
    .btn-outline {
      background: transparent; color: var(--text);
      padding: 16px 36px; border-radius: 4px; text-decoration: none;
      font-size: 16px; font-weight: 700; text-transform: uppercase;
      letter-spacing: 1px; transition: all 0.2s;
      border: 2px solid #333; cursor: pointer; display: inline-block;
    }
    .btn-outline:hover { border-color: var(--green); color: var(--green); }
    .hero-stats {
      margin-top: 56px; display: flex; gap: 40px;
      animation: fadeUp 0.7s 0.5s ease both;
    }
    .stat { display: flex; flex-direction: column; }
    .stat-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 36px; color: var(--green); line-height: 1;
    }
    .stat-label { font-size: 12px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; }

    /* jersey mockup floating */
    .hero-visual {
      position: absolute; right: -40px; top: 50%; transform: translateY(-50%);
      width: 520px; opacity: 0.15;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 420px; line-height: 1;
      color: var(--green);
      pointer-events: none;
      user-select: none;
    }

    /* ─── TICKER ─── */
    .ticker {
      background: var(--green); color: var(--black);
      padding: 12px 0; overflow: hidden; white-space: nowrap;
    }
    .ticker-inner {
      display: inline-flex; gap: 60px;
      animation: ticker 20s linear infinite;
    }
    .ticker-item {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 18px; letter-spacing: 2px;
      display: flex; align-items: center; gap: 16px;
    }
    .ticker-dot { width: 8px; height: 8px; background: var(--black); border-radius: 50%; }

    /* ─── SECTION COMMON ─── */
    section { padding: 100px 40px; }
    .section-label {
      font-size: 12px; text-transform: uppercase; letter-spacing: 3px;
      color: var(--green); font-weight: 700; margin-bottom: 12px;
    }
    .section-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(40px, 6vw, 72px);
      line-height: 1; letter-spacing: 1px; margin-bottom: 16px;
    }
    .section-sub { font-size: 17px; color: var(--muted); max-width: 520px; line-height: 1.7; }

    /* ─── PRODUCTS ─── */
    .products { background: var(--dark); }
    .products-header { text-align: center; margin-bottom: 56px; }
    .products-header .section-sub { margin: 0 auto; }
    .filter-tabs {
      display: flex; gap: 8px; justify-content: center;
      margin-top: 28px; flex-wrap: wrap;
    }
    .tab {
      padding: 8px 20px; border-radius: 100px; font-size: 13px;
      font-weight: 700; text-transform: uppercase; letter-spacing: 1px;
      cursor: pointer; transition: all 0.2s;
      border: 1px solid #2a2a2a; background: transparent; color: var(--muted);
    }
    .tab.active, .tab:hover { background: var(--green); color: var(--black); border-color: var(--green); }
    .products-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 24px; margin-top: 40px;
    }
    .product-card {
      background: var(--card); border-radius: 8px; overflow: hidden;
      border: 1px solid #1e1e1e; transition: all 0.3s; cursor: pointer;
      position: relative;
    }
    .product-card:hover { transform: translateY(-6px); border-color: #2e2e2e; box-shadow: 0 20px 60px rgba(0,0,0,0.5); }
    .product-img {
      height: 200px; display: flex; align-items: center; justify-content: center;
      font-size: 100px; position: relative; overflow: hidden;
    }
    .badge-hot {
      position: absolute; top: 12px; right: 12px;
      background: var(--red); color: white;
      font-size: 11px; font-weight: 700; text-transform: uppercase;
      letter-spacing: 1px; padding: 4px 10px; border-radius: 4px;
    }
    .badge-new {
      position: absolute; top: 12px; right: 12px;
      background: var(--yellow); color: var(--black);
      font-size: 11px; font-weight: 700; text-transform: uppercase;
      letter-spacing: 1px; padding: 4px 10px; border-radius: 4px;
    }
    .product-info { padding: 20px; }
    .product-club { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 2px; }
    .product-name { font-family: 'Barlow Condensed', sans-serif; font-size: 22px; font-weight: 900; margin: 4px 0 12px; }
    .product-footer { display: flex; align-items: center; justify-content: space-between; }
    .product-price { display: flex; align-items: baseline; gap: 8px; }
    .price-now { font-family: 'Bebas Neue', sans-serif; font-size: 28px; color: var(--green); }
    .price-was { font-size: 14px; color: var(--muted); text-decoration: line-through; }
    .add-btn {
      background: var(--green); color: var(--black);
      border: none; padding: 10px 16px; border-radius: 4px;
      font-size: 13px; font-weight: 700; cursor: pointer;
      text-transform: uppercase; letter-spacing: 1px; transition: all 0.2s;
    }
    .add-btn:hover { background: var(--green-dark); }

    /* ─── WHY US ─── */
    .why-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      gap: 24px; margin-top: 56px;
    }
    .why-card {
      background: var(--card); padding: 32px; border-radius: 8px;
      border: 1px solid #1e1e1e; transition: border-color 0.3s;
    }
    .why-card:hover { border-color: rgba(0,230,118,0.3); }
    .why-icon { font-size: 36px; margin-bottom: 16px; }
    .why-title { font-family: 'Barlow Condensed', sans-serif; font-size: 22px; font-weight: 900; margin-bottom: 8px; }
    .why-desc { font-size: 15px; color: var(--muted); line-height: 1.7; }

    /* ─── TESTIMONIALS ─── */
    .testimonials { background: var(--dark); }
    .testi-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 24px; margin-top: 56px;
    }
    .testi-card {
      background: var(--card); padding: 28px; border-radius: 8px;
      border: 1px solid #1e1e1e;
    }
    .stars { color: var(--yellow); font-size: 18px; margin-bottom: 16px; }
    .testi-text { font-size: 16px; line-height: 1.8; color: #ccc; margin-bottom: 20px; }
    .testi-author { display: flex; align-items: center; gap: 12px; }
    .avatar {
      width: 44px; height: 44px; border-radius: 50%;
      background: var(--green); color: var(--black);
      display: flex; align-items: center; justify-content: center;
      font-weight: 900; font-size: 16px;
    }
    .author-name { font-weight: 700; font-size: 15px; }
    .author-loc { font-size: 13px; color: var(--muted); }

    /* ─── HOW TO ORDER ─── */
    .steps { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 32px; margin-top: 56px; }
    .step { text-align: center; }
    .step-num {
      font-family: 'Bebas Neue', sans-serif; font-size: 80px;
      color: rgba(0,230,118,0.12); line-height: 1; margin-bottom: 4px;
    }
    .step-title { font-family: 'Barlow Condensed', sans-serif; font-size: 22px; font-weight: 900; margin-bottom: 8px; }
    .step-desc { font-size: 15px; color: var(--muted); line-height: 1.7; }

    /* ─── CTA BAND ─── */
    .cta-band {
      background: var(--green); color: var(--black);
      text-align: center; padding: 80px 40px;
    }
    .cta-band h2 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(48px, 7vw, 90px);
      letter-spacing: 2px; line-height: 1; margin-bottom: 16px;
    }
    .cta-band p { font-size: 18px; margin-bottom: 36px; opacity: 0.8; }
    .btn-dark {
      background: var(--black); color: var(--text);
      padding: 18px 48px; border-radius: 4px; text-decoration: none;
      font-size: 16px; font-weight: 900; text-transform: uppercase;
      letter-spacing: 1px; transition: all 0.2s; display: inline-block;
    }
    .btn-dark:hover { background: #1a1a1a; transform: translateY(-2px); }

    /* ─── FOOTER ─── */
    footer {
      background: var(--black); border-top: 1px solid #1a1a1a;
      padding: 60px 40px 32px; text-align: center;
    }
    .footer-logo {
      font-family: 'Bebas Neue', sans-serif; font-size: 36px;
      color: var(--green); letter-spacing: 2px; margin-bottom: 16px;
    }
    .footer-links { display: flex; gap: 24px; justify-content: center; flex-wrap: wrap; margin-bottom: 32px; }
    .footer-links a { color: var(--muted); text-decoration: none; font-size: 14px; transition: color 0.2s; }
    .footer-links a:hover { color: var(--green); }
    .footer-copy { font-size: 13px; color: #444; }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes ticker {
      from { transform: translateX(0); }
      to { transform: translateX(-50%); }
    }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 768px) {
      nav ul { display: none; }
      nav { padding: 14px 20px; }
      .hero { padding: 100px 20px 60px; }
      .hero-visual { display: none; }
      section { padding: 70px 20px; }
      .hero-stats { gap: 24px; }
      .cta-band { padding: 60px 20px; }
      footer { padding: 48px 20px 24px; }
    }
  </style>
</head>
<body>

<!-- NAVBAR -->
<nav>
  <div class="logo">Jersey<span>King</span></div>
  <ul>
    <li><a href="#produk">Produk</a></li>
    <li><a href="#kenapa">Kenapa Kami</a></li>
    <li><a href="#cara-order">Cara Order</a></li>
    <li><a href="#order" class="nav-cta">Order Sekarang</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-visual">⬛</div>

  <div class="hero-content">
    <div class="hero-badge">Penghantaran Seluruh Malaysia</div>
    <h1>
      <span class="sub">No.1 Supplier</span>
      Jersey
      <span class="highlight">Murah</span>
    </h1>
    <p class="hero-desc">
      Jersey kualiti premium dengan harga paling kompetitif di Malaysia. EPL, La Liga, Liga Super — semua ada. Gred AAA, borong atau runcit.
    </p>

    <div class="hero-price-strip">
      <div class="price-tag">RM45</div>
      <div class="price-info">
        <span class="from">Bermula dari</span>
        <span class="orig">RM120</span>
        <span class="save">🔥 Jimat sehingga 60%</span>
      </div>
    </div>

    <div class="hero-btns">
      <a href="#produk" class="btn-primary">Tengok Koleksi</a>
      <a href="https://wa.me/601XXXXXXXX?text=Saya%20nak%20tanya%20pasal%20jersey" class="btn-outline" target="_blank">💬 Whatsapp Kami</a>
    </div>

    <div class="hero-stats">
      <div class="stat"><span class="stat-num">5K+</span><span class="stat-label">Pelanggan Puas</span></div>
      <div class="stat"><span class="stat-num">200+</span><span class="stat-label">Jenis Jersey</span></div>
      <div class="stat"><span class="stat-num">4.9★</span><span class="stat-label">Rating Purata</span></div>
    </div>
  </div>
</section>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner">
    <span class="ticker-item"><span class="ticker-dot"></span> PENGHANTARAN 1-3 HARI BEKERJA</span>
    <span class="ticker-item"><span class="ticker-dot"></span> GRED AAA THAILAND</span>
    <span class="ticker-item"><span class="ticker-dot"></span> BORONG HARGA TERUS</span>
    <span class="ticker-item"><span class="ticker-dot"></span> COD LEMBAH KLANG</span>
    <span class="ticker-item"><span class="ticker-dot"></span> SAIZ S – 4XL ADA</span>
    <span class="ticker-item"><span class="ticker-dot"></span> PENAMBAHAN NAMA & NOMBOR</span>
    <span class="ticker-item"><span class="ticker-dot"></span> PENGHANTARAN 1-3 HARI BEKERJA</span>
    <span class="ticker-item"><span class="ticker-dot"></span> GRED AAA THAILAND</span>
    <span class="ticker-item"><span class="ticker-dot"></span> BORONG HARGA TERUS</span>
    <span class="ticker-item"><span class="ticker-dot"></span> COD LEMBAH KLANG</span>
    <span class="ticker-item"><span class="ticker-dot"></span> SAIZ S – 4XL ADA</span>
    <span class="ticker-item"><span class="ticker-dot"></span> PENAMBAHAN NAMA & NOMBOR</span>
  </div>
</div>

<!-- PRODUCTS -->
<section class="products" id="produk">
  <div class="products-header">
    <div class="section-label">Koleksi Terbaru</div>
    <h2 class="section-title">Pilih Jersey Kau</h2>
    <p class="section-sub">Stok sentiasa dikemaskini. Habis = habis. Jangan lepas peluang!</p>
    <div class="filter-tabs">
      <button class="tab active">Semua</button>
      <button class="tab">EPL</button>
      <button class="tab">La Liga</button>
      <button class="tab">Liga Super</button>
      <button class="tab">Negara</button>
    </div>
  </div>

  <div class="products-grid">

    <div class="product-card">
      <div class="product-img" style="background:linear-gradient(135deg,#e00018,#9e0012)">
        <span>⚽</span><span class="badge-hot">HOT</span>
      </div>
      <div class="product-info">
        <div class="product-club">Manchester United</div>
        <div class="product-name">Home Kit 2024/25</div>
        <div class="product-footer">
          <div class="product-price">
            <span class="price-now">RM55</span>
            <span class="price-was">RM130</span>
          </div>
          <button class="add-btn" onclick="orderWA('MU Home 24/25')">Order</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img" style="background:linear-gradient(135deg,#003da5,#001489)">
        <span>⚽</span><span class="badge-new">NEW</span>
      </div>
      <div class="product-info">
        <div class="product-club">Chelsea FC</div>
        <div class="product-name">Home Kit 2024/25</div>
        <div class="product-footer">
          <div class="product-price">
            <span class="price-now">RM55</span>
            <span class="price-was">RM130</span>
          </div>
          <button class="add-btn" onclick="orderWA('Chelsea Home 24/25')">Order</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img" style="background:linear-gradient(135deg,#004d98,#1d4384)">
        <span>⚽</span>
      </div>
      <div class="product-info">
        <div class="product-club">FC Barcelona</div>
        <div class="product-name">Home Kit 2024/25</div>
        <div class="product-footer">
          <div class="product-price">
            <span class="price-now">RM60</span>
            <span class="price-was">RM140</span>
          </div>
          <button class="add-btn" onclick="orderWA('Barcelona Home 24/25')">Order</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img" style="background:linear-gradient(135deg,#fff,#e8e8e8)">
        <span>⚽</span><span class="badge-hot">HOT</span>
      </div>
      <div class="product-info">
        <div class="product-club">Real Madrid</div>
        <div class="product-name">Home Kit 2024/25</div>
        <div class="product-footer">
          <div class="product-price">
            <span class="price-now">RM60</span>
            <span class="price-was">RM140</span>
          </div>
          <button class="add-btn" onclick="orderWA('Real Madrid Home 24/25')">Order</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img" style="background:linear-gradient(135deg,#ffcd00,#e6b800)">
        <span>⚽</span>
      </div>
      <div class="product-info">
        <div class="product-club">Malaysia</div>
        <div class="product-name">Harimau Malaya 2024</div>
        <div class="product-footer">
          <div class="product-price">
            <span class="price-now">RM45</span>
            <span class="price-was">RM110</span>
          </div>
          <button class="add-btn" onclick="orderWA('Malaysia Harimau Malaya 2024')">Order</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img" style="background:linear-gradient(135deg,#0057a8,#003d78)">
        <span>⚽</span><span class="badge-new">NEW</span>
      </div>
      <div class="product-info">
        <div class="product-club">JDT FC</div>
        <div class="product-name">Home Kit 2025</div>
        <div class="product-footer">
          <div class="product-price">
            <span class="price-now">RM50</span>
            <span class="price-was">RM120</span>
          </div>
          <button class="add-btn" onclick="orderWA('JDT Home 2025')">Order</button>
        </div>
      </div>
    </div>

  </div>

  <div style="text-align:center; margin-top:48px;">
    <a href="https://wa.me/601XXXXXXXX?text=Saya%20nak%20tengok%20semua%20stok%20jersey" class="btn-primary" target="_blank">Tengok Semua Koleksi →</a>
  </div>
</section>

<!-- WHY US -->
<section id="kenapa">
  <div style="max-width:600px">
    <div class="section-label">Kenapa Pilih Kami</div>
    <h2 class="section-title">Murah Bukan Bermakna Murahan</h2>
    <p class="section-sub">Kami supply jersey gred AAA Thailand yang sama kualiti jersey original — pada harga yang waras.</p>
  </div>

  <div class="why-grid">
    <div class="why-card">
      <div class="why-icon">🏆</div>
      <div class="why-title">Gred AAA Thailand</div>
      <div class="why-desc">Jahitan rapi, material wicking, logo embroidery. Kalah jersey ori pun tidak.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">💰</div>
      <div class="why-title">Harga Paling Murah</div>
      <div class="why-desc">Terus dari supplier. Tiada middleman. Harga borong ada untuk reseller.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">🚚</div>
      <div class="why-title">Penghantaran Laju</div>
      <div class="why-desc">1–3 hari bekerja Pos Laju / J&T. COD tersedia di sekitar Lembah Klang.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">✏️</div>
      <div class="why-title">Nama & Nombor Custom</div>
      <div class="why-desc">Tampal nama & nombor pilihan kau. Print heat-press atau embroidery tersedia.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">📦</div>
      <div class="why-title">Stok Luas</div>
      <div class="why-desc">200+ pilihan jersey dari EPL, La Liga, Bundesliga, Liga Super dan lebih.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">💬</div>
      <div class="why-title">Khidmat Pelanggan 24/7</div>
      <div class="why-desc">Ada soal jawab via WhatsApp. Cepat respon, ada after-sales support.</div>
    </div>
  </div>
</section>

<!-- HOW TO ORDER -->
<section style="background:var(--dark)" id="cara-order">
  <div style="text-align:center; max-width:600px; margin:0 auto">
    <div class="section-label">Mudah Je</div>
    <h2 class="section-title">Cara Nak Order</h2>
    <p class="section-sub">Proses order kami dibuat semudah mungkin — 4 langkah je!</p>
  </div>

  <div class="steps">
    <div class="step">
      <div class="step-num">01</div>
      <div class="step-title">Pilih Jersey</div>
      <div class="step-desc">Scroll katalog atau tanya kami di WhatsApp untuk stok terkini.</div>
    </div>
    <div class="step">
      <div class="step-num">02</div>
      <div class="step-title">Hantar Order</div>
      <div class="step-desc">Mesej kami nama jersey, saiz, nama & nombor (kalau nak custom).</div>
    </div>
    <div class="step">
      <div class="step-num">03</div>
      <div class="step-title">Buat Bayaran</div>
      <div class="step-desc">Bank transfer / TNG eWallet. Confirm bayaran — kami proses terus.</div>
    </div>
    <div class="step">
      <div class="step-num">04</div>
      <div class="step-title">Tunggu Sampai</div>
      <div class="step-desc">Tracking number akan dihantar. Jersey sampai dalam 1–3 hari bekerja!</div>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials">
  <div style="text-align:center; max-width:600px; margin:0 auto">
    <div class="section-label">Ulasan Pelanggan</div>
    <h2 class="section-title">Diorang Dah Cuba</h2>
    <p class="section-sub">Lebih 5,000 pelanggan berpuas hati seluruh Malaysia.</p>
  </div>

  <div class="testi-grid">
    <div class="testi-card">
      <div class="stars">★★★★★</div>
      <p class="testi-text">"Ambil 10 biji untuk tournament futsal. Kualiti memang tiptop, jahitan kemas. Harga pun sangat berbaloi. Confirm repeat order!"</p>
      <div class="testi-author">
        <div class="avatar">A</div>
        <div>
          <div class="author-name">Azri Hakim</div>
          <div class="author-loc">📍 Shah Alam, Selangor</div>
        </div>
      </div>
    </div>
    <div class="testi-card">
      <div class="stars">★★★★★</div>
      <p class="testi-text">"Dah beli jersey EPL dari sini 3 kali. Tak pernah kecewa. Respon pun laju gila. COD pun ada. Trusted seller!"</p>
      <div class="testi-author">
        <div class="avatar">F</div>
        <div>
          <div class="author-name">Farah Nadia</div>
          <div class="author-loc">📍 Cheras, KL</div>
        </div>
      </div>
    </div>
    <div class="testi-card">
      <div class="stars">★★★★★</div>
      <p class="testi-text">"Jersey MU yang aku beli — nama & nombor pun ada letak. Kawan ingat ori. Lepas ni kalau ada baju bola, sini je aku cari."</p>
      <div class="testi-author">
        <div class="avatar">H</div>
        <div>
          <div class="author-name">Hafizuddin</div>
          <div class="author-loc">📍 Johor Bahru, Johor</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA BAND -->
<div class="cta-band" id="order">
  <h2>JANGAN LEPAS PELUANG!</h2>
  <p>Stok terhad. Order sekarang sebelum kehabisan. Whatsapp kami terus untuk harga terbaik.</p>
  <a href="https://wa.me/601XXXXXXXX?text=Saya%20nak%20order%20jersey%20dari%20JerseyKing" class="btn-dark" target="_blank">💬 Order via WhatsApp Sekarang</a>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">JerseyKing</div>
  <div class="footer-links">
    <a href="#home">Home</a>
    <a href="#produk">Produk</a>
    <a href="#kenapa">Kenapa Kami</a>
    <a href="#cara-order">Cara Order</a>
    <a href="https://wa.me/601XXXXXXXX" target="_blank">WhatsApp</a>
  </div>
  <p class="footer-copy">© 2025 JerseyKing Malaysia · Semua Hak Terpelihara · Made with ❤️ for bola lovers</p>
</footer>

<script>
  // Filter tabs
  document.querySelectorAll('.tab').forEach(tab => {
    tab.addEventListener('click', () => {
      document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
      tab.classList.add('active');
    });
  });

  // WhatsApp order helper
  function orderWA(jersey) {
    const msg = encodeURIComponent(`Salam! Saya nak order:\n\n🛒 *${jersey}*\n\nSaiz: \nNama (kalau nak): \nNombor (kalau nak): \n\nBoleh confirm stok & harga?`);
    window.open(`https://wa.me/601XXXXXXXX?text=${msg}`, '_blank');
  }

  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.product-card, .why-card, .testi-card, .step').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(30px)';
    el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
