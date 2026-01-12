# playfulness-V2
<!doctype html>
<html lang="ja">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="theme-color" content="#0b1116" />
  <title>Playfulness｜続けることが、かっこよくなる。</title>
  <meta name="description" content="習慣化アプリ Playfulness。続かない日々を、ゲーム感覚でスマートに変える。ダーク×ミントの洗練UI。" />
  <style>
    :root{
      --bg: #070b10;
      --panel: rgba(255,255,255,.06);
      --panel2: rgba(255,255,255,.08);
      --text: rgba(255,255,255,.92);
      --muted: rgba(255,255,255,.70);
      --dim: rgba(255,255,255,.55);
      --line: rgba(255,255,255,.12);
      --mint: #48f6d2;
      --mint2:#20c9b1;
      --danger:#ff5a8a;
      --shadow: 0 18px 60px rgba(0,0,0,.55);
      --radius: 18px;
      --radius2: 26px;
      --max: 1120px;
      --focus: 0 0 0 3px rgba(72,246,210,.22);
      --font: ui-sans-serif, system-ui, -apple-system, "Segoe UI", "Hiragino Sans", "Noto Sans JP", "Yu Gothic", "Meiryo", Arial, sans-serif;
    }

    *{ box-sizing:border-box; }
    html,body{ height:100%; }
    body{
      margin:0;
      font-family: var(--font);
      color: var(--text);
      background:
        radial-gradient(1200px 700px at 18% 12%, rgba(72,246,210,.14), transparent 55%),
        radial-gradient(900px 600px at 85% 22%, rgba(96,120,255,.10), transparent 55%),
        radial-gradient(800px 500px at 50% 95%, rgba(255,90,138,.06), transparent 60%),
        linear-gradient(180deg, #060a0f 0%, #05070c 45%, #04060a 100%);
      overflow-x:hidden;
    }

    a{ color:inherit; text-decoration:none; }
    .container{ width:min(var(--max), calc(100% - 40px)); margin:0 auto; }
    .pill{
      display:inline-flex; align-items:center; gap:10px;
      padding:8px 12px;
      border:1px solid var(--line);
      background: rgba(255,255,255,.04);
      border-radius: 999px;
      color: var(--muted);
      backdrop-filter: blur(10px);
    }
    .dot{
      width:9px; height:9px; border-radius:999px;
      background: var(--mint);
      box-shadow: 0 0 18px rgba(72,246,210,.65);
    }
    .kicker{ font-weight:600; letter-spacing:.06em; text-transform:uppercase; font-size:12px; }
    .btn{
      display:inline-flex; align-items:center; justify-content:center; gap:10px;
      padding: 14px 18px;
      border-radius: 14px;
      border:1px solid transparent;
      font-weight:700;
      cursor:pointer;
      transition: transform .12s ease, box-shadow .12s ease, background .12s ease, border-color .12s ease;
      user-select:none;
      will-change: transform;
    }
    .btn:focus-visible{ outline:none; box-shadow: var(--focus); }
    .btn:hover{ transform: translateY(-1px); }
    .btn:active{ transform: translateY(0px) scale(.99); }
    .btn-primary{
      background: linear-gradient(135deg, var(--mint) 0%, #72ffd7 40%, #2be6c8 100%);
      color:#041013;
      box-shadow: 0 14px 40px rgba(72,246,210,.22);
    }
    .btn-ghost{
      background: rgba(255,255,255,.05);
      border-color: rgba(255,255,255,.14);
      color: var(--text);
    }
    .btn-link{
      background: transparent;
      border-color: transparent;
      color: var(--mint);
      padding: 12px 6px;
    }

    /* Header */
    header{
      position: sticky;
      top:0;
      z-index: 50;
      backdrop-filter: blur(14px);
      background: linear-gradient(180deg, rgba(5,8,12,.72) 0%, rgba(5,8,12,.45) 100%);
      border-bottom: 1px solid rgba(255,255,255,.08);
    }
    .nav{
      display:flex; align-items:center; justify-content:space-between;
      padding: 14px 0;
      gap: 14px;
    }
    .brand{
      display:flex; align-items:center; gap:10px;
      font-weight:900;
      letter-spacing: .02em;
    }
    .logo{
      width:34px; height:34px; border-radius:12px;
      background: radial-gradient(circle at 30% 30%, rgba(255,255,255,.25), transparent 55%),
                  linear-gradient(135deg, rgba(72,246,210,1), rgba(32,201,177,1));
      box-shadow: 0 10px 30px rgba(72,246,210,.18);
      border: 1px solid rgba(255,255,255,.18);
    }
    .navlinks{
      display:none;
      gap: 18px;
      color: var(--muted);
      font-weight:600;
      font-size: 14px;
    }
    .navlinks a{ padding:10px 8px; border-radius: 10px; }
    .navlinks a:hover{ background: rgba(255,255,255,.05); color: var(--text); }
    .navcta{ display:flex; align-items:center; gap:10px; }

    /* Hero */
    .hero{
      padding: 42px 0 34px;
    }
    .hero-grid{
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 26px;
      align-items: center;
    }
    .hero h1{
      font-size: clamp(32px, 4.4vw, 54px);
      line-height: 1.05;
      margin: 14px 0 12px;
      letter-spacing: -.02em;
    }
    .hero p{
      color: var(--muted);
      font-size: clamp(15px, 1.5vw, 18px);
      line-height: 1.8;
      margin: 0 0 18px;
      max-width: 46ch;
    }
    .hero-actions{
      display:flex;
      flex-wrap: wrap;
      gap: 10px;
      align-items:center;
      margin-top: 6px;
    }
    .mini{
      display:flex; gap:16px; align-items:center; margin-top: 18px; color: var(--dim);
      font-size: 13px;
    }
    .mini strong{ color: var(--text); }
    .mini .sep{ width:1px; height:12px; background: rgba(255,255,255,.18); }

    .hero-card{
      position:relative;
      border-radius: var(--radius2);
      border: 1px solid rgba(255,255,255,.10);
      background:
        radial-gradient(700px 380px at 10% 10%, rgba(72,246,210,.16), transparent 60%),
        radial-gradient(600px 320px at 90% 20%, rgba(96,120,255,.14), transparent 62%),
        linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.04));
      box-shadow: var(--shadow);
      overflow:hidden;
      padding: 16px;
      min-height: 420px;
    }
    .hero-card .frame{
      border-radius: 22px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.22);
      height: 100%;
      overflow:hidden;
      position:relative;
    }
    .hero-card .badge{
      position:absolute;
      top:14px; left:14px;
      background: rgba(5,8,12,.55);
      border:1px solid rgba(255,255,255,.12);
      padding: 8px 10px;
      border-radius: 999px;
      font-size: 12px;
      color: var(--muted);
      backdrop-filter: blur(10px);
    }
    .hero-card .badge b{ color: var(--text); }
    .anime-placeholder{
      position:absolute; inset:0;
      display:grid;
      place-items:center;
      padding: 18px;
      background:
        radial-gradient(120px 120px at 40% 36%, rgba(255,255,255,.22), transparent 60%),
        radial-gradient(140px 140px at 62% 40%, rgba(72,246,210,.20), transparent 60%),
        radial-gradient(160px 160px at 55% 65%, rgba(255,90,138,.12), transparent 62%),
        linear-gradient(135deg, rgba(255,255,255,.05), rgba(255,255,255,.02));
    }
    .anime-placeholder .note{
      text-align:center;
      color: rgba(255,255,255,.72);
      max-width: 42ch;
      font-size: 13px;
      line-height: 1.8;
    }
    .anime-placeholder .imgbox{
      width: 100%;
      height: 64%;
      border-radius: 18px;
      border:1px dashed rgba(255,255,255,.22);
      background: linear-gradient(135deg, rgba(72,246,210,.08), rgba(96,120,255,.06));
      display:grid;
      place-items:center;
      margin-bottom: 12px;
    }
    .anime-placeholder .imgbox span{
      font-weight:800;
      color: rgba(255,255,255,.78);
      letter-spacing:.04em;
    }
    .hero-card .hud{
      position:absolute; left:14px; right:14px; bottom:14px;
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }
    .hud .chip{
      border-radius: 16px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.28);
      padding: 12px 12px;
      backdrop-filter: blur(10px);
    }
    .chip .t{ font-size: 12px; color: var(--dim); }
    .chip .v{ font-size: 16px; font-weight: 900; margin-top: 4px; }
    .chip .v em{ font-style: normal; color: var(--mint); }

    /* Sections */
    section{ padding: 58px 0; }
    .section-head{
      display:flex; align-items:flex-end; justify-content:space-between;
      gap: 16px;
      margin-bottom: 18px;
    }
    h2{
      font-size: clamp(22px, 2.7vw, 32px);
      margin: 0;
      letter-spacing:-.01em;
    }
    .lead{
      color: var(--muted);
      margin: 6px 0 0;
      line-height: 1.85;
      max-width: 70ch;
    }

    .grid-3{ display:grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
    .grid-2{ display:grid; grid-template-columns: repeat(2, 1fr); gap: 14px; }
    .grid-6{ display:grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }

    .card{
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.05);
      border-radius: var(--radius);
      padding: 18px;
      box-shadow: 0 14px 40px rgba(0,0,0,.22);
    }
    .card.soft{
      background: linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.04));
    }
    .icon{
      width: 40px; height: 40px;
      border-radius: 14px;
      background:
        radial-gradient(circle at 30% 30%, rgba(255,255,255,.18), transparent 58%),
        linear-gradient(135deg, rgba(72,246,210,.95), rgba(32,201,177,.85));
      border: 1px solid rgba(255,255,255,.16);
      box-shadow: 0 14px 34px rgba(72,246,210,.12);
      margin-bottom: 12px;
    }
    .card h3{ margin: 0 0 6px; font-size: 16px; letter-spacing: -.01em; }
    .card p{ margin: 0; color: var(--muted); line-height: 1.8; font-size: 14px; }
    .muted{ color: var(--muted); }

    /* Mechanism */
    .mechanism{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
      align-items: stretch;
    }
    .meter{
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.22);
      padding: 18px;
      position:relative;
      overflow:hidden;
    }
    .meter:before{
      content:"";
      position:absolute; inset:-80px -80px auto auto;
      width: 220px; height: 220px;
      background: radial-gradient(circle at 30% 30%, rgba(72,246,210,.25), transparent 60%);
      transform: rotate(12deg);
      pointer-events:none;
    }
    .bar{
      height: 12px;
      border-radius: 999px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.06);
      overflow:hidden;
      margin-top: 10px;
    }
    .bar > div{
      height:100%;
      width: 78%;
      background: linear-gradient(90deg, rgba(72,246,210,.95), rgba(96,120,255,.45));
      border-radius: 999px;
      box-shadow: 0 0 24px rgba(72,246,210,.30);
    }
    .meter .row{
      display:flex; align-items:baseline; justify-content:space-between; gap: 10px;
    }
    .meter .row b{ font-size: 14px; }
    .meter .row span{ color: var(--dim); font-size: 12px; }

    /* Steps */
    .step{
      display:flex; gap: 14px;
      align-items:flex-start;
    }
    .num{
      min-width: 40px; height: 40px;
      border-radius: 14px;
      display:grid; place-items:center;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.06);
      color: var(--mint);
      font-weight: 900;
      box-shadow: 0 12px 30px rgba(0,0,0,.2);
    }
    .step h3{ margin: 0 0 6px; }
    .step p{ margin: 0; color: var(--muted); line-height: 1.85; font-size: 14px; }

    /* Pricing */
    .pricing{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
      align-items: stretch;
    }
    .price-card{
      position:relative;
      overflow:hidden;
    }
    .price-card.featured{
      border-color: rgba(72,246,210,.35);
      background:
        radial-gradient(600px 320px at 20% 10%, rgba(72,246,210,.18), transparent 60%),
        linear-gradient(180deg, rgba(255,255,255,.07), rgba(255,255,255,.04));
      box-shadow: 0 18px 60px rgba(72,246,210,.10), 0 22px 80px rgba(0,0,0,.35);
    }
    .ribbon{
      position:absolute;
      top: 16px; right: 16px;
      font-size: 12px;
      padding: 7px 10px;
      border-radius: 999px;
      background: rgba(72,246,210,.14);
      border: 1px solid rgba(72,246,210,.35);
      color: var(--mint);
      font-weight: 800;
      backdrop-filter: blur(10px);
    }
    .price{
      display:flex; align-items:baseline; gap: 8px;
      margin: 10px 0 12px;
    }
    .price .yen{
      font-size: 34px;
      font-weight: 950;
      letter-spacing: -.02em;
    }
    .price .per{
      color: var(--dim);
      font-size: 13px;
    }
    .list{ margin: 10px 0 0; padding: 0; list-style:none; display:grid; gap: 10px; }
    .list li{
      display:flex; gap: 10px; align-items:flex-start;
      color: var(--muted);
      font-size: 14px;
      line-height: 1.6;
    }
    .check{
      width: 18px; height: 18px; border-radius: 6px;
      background: rgba(72,246,210,.14);
      border: 1px solid rgba(72,246,210,.28);
      display:grid; place-items:center;
      flex: 0 0 auto;
      margin-top: 2px;
    }
    .check svg{ width: 12px; height: 12px; fill: var(--mint); }

    /* FAQ */
    .faq{
      display:grid;
      grid-template-columns: 1fr;
      gap: 10px;
      margin-top: 14px;
    }
    details{
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.05);
      overflow:hidden;
    }
    summary{
      list-style:none;
      cursor:pointer;
      padding: 16px 16px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap: 12px;
      font-weight: 800;
      color: var(--text);
    }
    summary::-webkit-details-marker{ display:none; }
    .faq-body{
      padding: 0 16px 16px;
      color: var(--muted);
      line-height: 1.9;
      font-size: 14px;
    }
    .plus{
      width: 34px; height: 34px;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.18);
      display:grid; place-items:center;
      flex: 0 0 auto;
      transition: transform .18s ease;
    }
    details[open] .plus{ transform: rotate(45deg); }
    .plus:before, .plus:after{
      content:"";
      position:absolute;
    }
    .plus svg{ width: 16px; height: 16px; fill: rgba(255,255,255,.88); }

    /* Final CTA */
    .final{
      padding: 56px 0 74px;
    }
    .cta-panel{
      border-radius: 26px;
      border: 1px solid rgba(255,255,255,.10);
      background:
        radial-gradient(900px 420px at 15% 20%, rgba(72,246,210,.18), transparent 60%),
        radial-gradient(700px 360px at 85% 30%, rgba(96,120,255,.12), transparent 62%),
        linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.04));
      box-shadow: var(--shadow);
      padding: 26px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap: 18px;
      overflow:hidden;
      position:relative;
    }
    .cta-panel:after{
      content:"";
      position:absolute;
      inset:auto -120px -120px auto;
      width: 280px; height: 280px;
      background: radial-gradient(circle at 30% 30%, rgba(72,246,210,.22), transparent 60%);
      transform: rotate(-10deg);
      pointer-events:none;
    }
    .cta-panel h2{ margin: 0; }
    .cta-panel p{ margin: 8px 0 0; color: var(--muted); line-height: 1.85; }
    footer{
      padding: 22px 0 38px;
      border-top: 1px solid rgba(255,255,255,.08);
      color: var(--dim);
      font-size: 13px;
    }

    /* Small helpers */
    .split{
      display:flex; gap: 10px; flex-wrap: wrap;
      align-items:center;
    }
    .tag{
      display:inline-flex; align-items:center; gap:8px;
      padding: 8px 10px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.16);
      color: var(--muted);
      font-size: 12px;
    }
    .tag b{ color: var(--text); font-weight: 800; }

    /* Responsive */
    @media (max-width: 980px){
      .hero-grid{ grid-template-columns: 1fr; }
      .hero-card{ min-height: 420px; }
      .navlinks{ display:none !important; }
      .grid-6{ grid-template-columns: repeat(2, 1fr); }
      .mechanism{ grid-template-columns: 1fr; }
      .pricing{ grid-template-columns: 1fr; }
      .cta-panel{ flex-direction: column; align-items:flex-start; }
    }
    @media (min-width: 981px){
      .navlinks{ display:flex; }
    }
    @media (max-width: 640px){
      section{ padding: 44px 0; }
      .grid-3{ grid-template-columns: 1fr; }
      .grid-2{ grid-template-columns: 1fr; }
      .grid-6{ grid-template-columns: 1fr; }
      .hero-actions .btn{ width: 100%; }
      .hero-card .hud{ grid-template-columns: 1fr; }
      .cta-panel{ padding: 20px; }
    }
  </style>
</head>

<body>
  <!-- Header -->
  <header>
    <div class="container">
      <div class="nav">
        <a class="brand" href="#top" aria-label="Playfulness">
          <span class="logo" aria-hidden="true"></span>
          <span>Playfulness</span>
        </a>

        <nav class="navlinks" aria-label="セクション">
          <a href="#pain">悩み</a>
          <a href="#mechanism">仕組み</a>
          <a href="#features">機能</a>
          <a href="#howto">使い方</a>
          <a href="#pricing">料金</a>
          <a href="#faq">FAQ</a>
        </nav>

        <div class="navcta">
          <a class="btn btn-ghost" href="https://playfulnessv2.netlify.app/" target="_blank" rel="noopener">デモを見る</a>
          <a class="btn btn-primary" href="https://playfulnessv2.netlify.app/" target="_blank" rel="noopener">今すぐ始める</a>
        </div>
      </div>
    </div>
  </header>

  <!-- Hero -->
  <main id="top" class="hero">
    <div class="container">
      <div class="hero-grid">
        <div>
          <span class="pill">
            <span class="dot" aria-hidden="true"></span>
            <span class="kicker">Habit × Game × Stylish</span>
          </span>

          <h1>続けることが、<br/>かっこよくなる。</h1>
          <p>
            習慣が続かない日々を、<b>スマートにゲーム化</b>。
            ミントのアクセントが映えるダークUIで、毎日の「やる」を気持ちよく積み上げよう。
          </p>

          <div class="hero-actions">
            <a class="btn btn-primary" href="https://playfulnessv2.netlify.app/" target="_blank" rel="noopener">
              主要CTA：デモへ
              <span aria-hidden="true">→</span>
            </a>
            <a class="btn btn-ghost" href="#pricing">料金を見る</a>
            <a class="btn btn-link" href="#features">機能をチェック</a>
          </div>

          <div class="mini" aria-label="補足情報">
            <span><strong>学生</strong>も<strong>社会人</strong>もOK</span>
            <span class="sep" aria-hidden="true"></span>
            <span>1日1分から</span>
            <span class="sep" aria-hidden="true"></span>
            <span>続けやすさ設計</span>
          </div>
        </div>

        <aside class="hero-card" aria-label="ビジュアル">
          <div class="frame">
            <div class="badge"><b>Anime Girl</b> Visual（プレースホルダー）</div>

            <!-- 画像プレースホルダー（アニメ調美女を差し替えOK） -->
            <div class="anime-placeholder">
              <div style="width:100%;">
                <div class="imgbox" role="img" aria-label="アニメ調美女の画像プレースホルダー">
                  <span>IMAGE PLACEHOLDER</span>
                </div>
                <div class="note">
                  ここに「アニメ調美女」の画像を差し替えてください。<br/>
                  例：<code>&lt;img src="your-image.jpg" /&gt;</code>
                </div>
              </div>
            </div>

            <!-- HUD -->
            <div class="hud" aria-hidden="true">
              <div class="chip">
                <div class="t">今日のミッション</div>
                <div class="v"><em>3</em> / 5 完了</div>
              </div>
              <div class="chip">
                <div class="t">ストリーク</div>
                <div class="v"><em>12</em> days</div>
              </div>
            </div>
          </div>
        </aside>
      </div>
    </div>
  </main>

  <!-- Pain / Empathy -->
  <section id="pain">
    <div class="container">
      <div class="section-head">
        <div>
          <h2>「続かない」は、あなたのせいじゃない。</h2>
          <p class="lead">
            意志より先に、生活は押し寄せる。やる気があっても、毎日は忙しい。
            Playfulnessは、<b>気合いに頼らない</b>続け方をデザインします。
          </p>
        </div>
      </div>

      <div class="grid-3">
        <div class="card soft">
          <div class="icon" aria-hidden="true"></div>
          <h3>三日坊主がデフォ</h3>
          <p>「また途切れた…」の自己嫌悪ループ。継続は才能じゃなく、仕組みで作れる。</p>
        </div>
        <div class="card soft">
          <div class="icon" aria-hidden="true"></div>
          <h3>やることが増えすぎる</h3>
          <p>勉強・仕事・家事・運動…全部は無理。だからこそ、優先度の見える化が効く。</p>
        </div>
        <div class="card soft">
          <div class="icon" aria-hidden="true"></div>
          <h3>モチベが日替わり</h3>
          <p>気分で崩れる設計は、最初から負け。気分がなくても回る「軽さ」が正義。</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Mechanism -->
  <section id="mechanism">
    <div class="container">
      <div class="section-head">
        <div>
          <h2>解決の仕組み：小さく勝って、積み上げる。</h2>
          <p class="lead">
            Playfulnessは、達成を「快感」に変換する3レイヤー設計。
            <b>見える → すぐ終わる → ちゃんと褒める</b>で、継続の体温を上げます。
          </p>
        </div>
      </div>

      <div class="mechanism">
        <div class="meter">
          <div class="row">
            <b>① 見える化（今日やることが一目でわかる）</b>
            <span>迷いを削る</span>
          </div>
          <div class="bar" aria-hidden="true"><div></div></div>
          <p class="muted" style="margin:12px 0 0; line-height:1.9;">
            予定が曖昧だと、脳は先延ばしを選びがち。タスクを短く切って、判断コストを下げます。
          </p>
        </div>

        <div class="meter">
          <div class="row">
            <b>② ミニミッション化（1分で終わる設計）</b>
            <span>摩擦を削る</span>
          </div>
          <div class="bar" aria-hidden="true"><div style="width:66%"></div></div>
          <p class="muted" style="margin:12px 0 0; line-height:1.9;">
            「始める」が一番重い。最初の一歩を軽くすると、勝手に2歩目が出ます。
          </p>
        </div>

        <div class="meter">
          <div class="row">
            <b>③ 報酬設計（達成が気持ちいい）</b>
            <span>快感を足す</span>
          </div>
          <div class="bar" aria-hidden="true"><div style="width:82%"></div></div>
          <p class="muted" style="margin:12px 0 0; line-height:1.9;">
            続けたくなるのは「自分、いい感じ」って思える瞬間。小さな成功体験を連打します。
          </p>
        </div>

        <div class="meter">
          <div class="row">
            <b>まとめ：気合い不要のループ</b>
            <span>再現性</span>
          </div>
          <div class="split" style="margin-top:12px;">
            <span class="tag"><b>見える</b> → 迷わない</span>
            <span class="tag"><b>軽い</b> → 始めやすい</span>
            <span class="tag"><b>褒める</b> → 続けたくなる</span>
          </div>
          <p class="muted" style="margin:12px 0 0; line-height:1.9;">
            その結果、「続いた」がアイデンティティになる。つまり、かっこいい。
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Features -->
  <section id="features">
    <div class="container">
      <div class="section-head">
        <div>
          <h2>機能：ちゃんと続くために、全部いる。</h2>
          <p class="lead">
            見た目だけじゃなく、中身も勝負。習慣化に必要な要素を、ミニマルに詰め込みました。
          </p>
        </div>
      </div>

      <div class="grid-6">
        <div class="card">
          <div class="icon" aria-hidden="true"></div>
          <h3>デイリー習慣ボード</h3>
          <p>今日の「やる」を一画面に集約。迷いをゼロへ。</p>
        </div>

        <div class="card">
          <div class="icon" aria-hidden="true"></div>
          <h3>ストリーク＆履歴</h3>
          <p>続いた日が可視化されると、途中でやめづらくなる。</p>
        </div>

        <div class="card">
          <div class="icon" aria-hidden="true"></div>
          <h3>ごほうび（ポイント/コイン）</h3>
          <p>達成の気持ちよさを、ちゃんと形にして残す。</p>
        </div>

        <div class="card">
          <div class="icon" aria-hidden="true"></div>
          <h3>リマインド（やさしめ）</h3>
          <p>追い詰めない通知。戻ってこれる余白が継続を生む。</p>
        </div>

        <div class="card">
          <div class="icon" aria-hidden="true"></div>
          <h3>目標の分解（ミニ化）</h3>
          <p>「大きい目標」を、今日できるサイズへ落とす。</p>
        </div>

        <div class="card">
          <div class="icon" aria-hidden="true"></div>
          <h3>ダーク×ミントの集中UI</h3>
          <p>視線が散らない。気分が上がる。だから開きたくなる。</p>
        </div>
      </div>
    </div>
  </section>

  <!-- How to use -->
  <section id="howto">
    <div class="container">
      <div class="section-head">
        <div>
          <h2>使い方：3ステップで、今日から回る。</h2>
          <p class="lead">複雑な設定は不要。まずは「小さく」始めて、勝手に育てるのが正解。</p>
        </div>
      </div>

      <div class="grid-3">
        <div class="card soft">
          <div class="step">
            <div class="num">1</div>
            <div>
              <h3>習慣を1つだけ登録</h3>
              <p>最初は「英単語3つ」「腕立て5回」みたいな軽さでOK。</p>
            </div>
          </div>
        </div>

        <div class="card soft">
          <div class="step">
            <div class="num">2</div>
            <div>
              <h3>できたら即チェック</h3>
              <p>達成の瞬間に記録するほど、脳が「気持ちいい」を覚える。</p>
            </div>
          </div>
        </div>

        <div class="card soft">
          <div class="step">
            <div class="num">3</div>
            <div>
              <h3>余裕が出たら増やす</h3>
              <p>いきなり完璧を狙わない。積み上げは、見た目以上に強い。</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing -->
  <section id="pricing">
    <div class="container">
      <div class="section-head">
        <div>
          <h2>料金：自分のペースに合わせて。</h2>
          <p class="lead">※表示はサンプルです（プレースホルダー）。実際の価格に合わせて文言を調整できます。</p>
        </div>
      </div>

      <div class="pricing">
        <div class="card price-card">
          <h3>Starter</h3>
          <div class="price">
            <div class="yen">¥0</div>
            <div class="per">/ month</div>
          </div>
          <p class="muted">まずは触ってみる。軽く始める人向け。</p>
          <ul class="list">
            <li><span class="check" aria-hidden="true">
              <svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg>
            </span>基本の習慣トラッキング</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>履歴の閲覧</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>最低限のリマインド</li>
          </ul>
          <div style="margin-top:16px;">
            <a class="btn btn-ghost" href="https://playfulnessv2.netlify.app/" target="_blank" rel="noopener" style="width:100%;">無料で試す</a>
          </div>
        </div>

        <div class="card price-card featured">
          <div class="ribbon">人気</div>
          <h3>Plus</h3>
          <div class="price">
            <div class="yen">¥980</div>
            <div class="per">/ month</div>
          </div>
          <p class="muted">習慣化を本気で回す。いちばんバランス。</p>
          <ul class="list">
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>ポイント/コイン報酬</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>目標の分解テンプレ</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>継続レポート（週次）</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>通知の細かい調整</li>
          </ul>
          <div style="margin-top:16px;">
            <a class="btn btn-primary" href="https://playfulnessv2.netlify.app/" target="_blank" rel="noopener" style="width:100%;">Plusで始める</a>
          </div>
        </div>

        <div class="card price-card">
          <h3>Team</h3>
          <div class="price">
            <div class="yen">¥2,980</div>
            <div class="per">/ month</div>
          </div>
          <p class="muted">仲間と続ける。ゆるい連帯が最強の継続力。</p>
          <ul class="list">
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>チームボード</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>ランキング（任意）</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>共有ミッション</li>
            <li><span class="check" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M9.2 16.6 4.9 12.3l1.4-1.4 2.9 2.9 8-8 1.4 1.4z"/></svg></span>管理者向けレポート</li>
          </ul>
          <div style="margin-top:16px;">
            <a class="btn btn-ghost" href="https://playfulnessv2.netlify.app/" target="_blank" rel="noopener" style="width:100%;">チームで試す</a>
          </div>
        </div>
      </div>

      <p class="muted" style="margin-top:14px; font-size:12px; line-height:1.7;">
        ※価格・機能はサンプルです。実際のサブスク仕様に合わせて「表現」と「特典」を整えると、さらに刺さります。
      </p>
    </div>
  </section>

  <!-- FAQ -->
  <section id="faq">
    <div class="container">
      <div class="section-head">
        <div>
          <h2>FAQ</h2>
          <p class="lead">よくある質問に先回り。ここで不安を消して、安心して始めよう。</p>
        </div>
      </div>

      <div class="faq" role="list">
        <details>
          <summary>
            習慣が本当に続くようになりますか？
            <span class="plus" aria-hidden="true">
              <svg viewBox="0 0 24 24"><path d="M11 5h2v14h-2zM5 11h14v2H5z"/></svg>
            </span>
          </summary>
          <div class="faq-body">
            続く確率を上げるのは「根性」じゃなく「摩擦の削減」です。Playfulnessは、始める負担を小さくし、達成が気持ちいい設計に寄せています。
            まずは1分タスクから回すのがおすすめ。
          </div>
        </details>

        <details>
          <summary>
            三日坊主でも大丈夫？
            <span class="plus" aria-hidden="true">
              <svg viewBox="0 0 24 24"><path d="M11 5h2v14h-2zM5 11h14v2H5z"/></svg>
            </span>
          </summary>
          <div class="faq-body">
            もちろん。むしろ三日坊主の人向けです。「完璧にやる」じゃなく「戻ってこれる」設計なので、途切れても再開しやすいです。
          </div>
        </details>

        <details>
          <summary>
            何から始めるのが正解？
            <span class="plus" aria-hidden="true">
              <svg viewBox="0 0 24 24"><path d="M11 5h2v14h-2zM5 11h14v2H5z"/></svg>
            </span>
          </summary>
          <div class="faq-body">
            いちばん効果が出やすいのは「毎日やりたいけど重いこと」を、超ミニにすることです。
            例：筋トレ→腕立て5回、勉強→単語3つ、片付け→机の上だけ、など。
          </div>
        </details>

        <details>
          <summary>
            スマホでもPCでも使えますか？
            <span class="plus" aria-hidden="true">
              <svg viewBox="0 0 24 24"><path d="M11 5h2v14h-2zM5 11h14v2H5z"/></svg>
            </span>
          </summary>
          <div class="faq-body">
            はい。レスポンシブ前提の設計です。移動中はスマホ、作業中はPCなど、生活に合わせて使い分けできます（デモページで確認できます）。
          </div>
        </details>

        <details>
          <summary>
            料金プランは後から変更できますか？
            <span class="plus" aria-hidden="true">
              <svg viewBox="0 0 24 24"><path d="M11 5h2v14h-2zM5 11h14v2H5z"/></svg>
            </span>
          </summary>
          <div class="faq-body">
            変更できる前提で設計すると離脱が減ります。LP上も「いつでも変更OK」「キャンセル簡単」などを明記すると安心感が出ます。
          </div>
        </details>
      </div>
    </div>
  </section>

  <!-- Final CTA -->
  <section class="final">
    <div class="container">
      <div class="cta-panel">
        <div>
          <h2>今日の1分が、未来の自分を作る。</h2>
          <p>
            洗練されたダークUIで、習慣を「気合い」から解放。<br/>
            Playfulnessで、続ける自分をデザインしよう。
          </p>
        </div>
        <div class="hero-actions" style="margin:0;">
          <a class="btn btn-primary" href="https://playfulnessv2.netlify.app/" target="_blank" rel="noopener">今すぐデモへ →</a>
          <a class="btn btn-ghost" href="#faq">不安を解消する</a>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      <div style="display:flex; justify-content:space-between; gap:12px; flex-wrap:wrap;">
        <div>© <span id="y"></span> Playfulness</div>
        <div style="color:rgba(255,255,255,.55);">Dark × Mint / One-page LP (Single HTML)</div>
      </div>
    </div>
  </footer>

  <script>
    // 年表示
    document.getElementById("y").textContent = new Date().getFullYear();

    // FAQ：アコーディオン（1つだけ開く挙動）
    const faqs = Array.from(document.querySelectorAll("#faq details"));
    faqs.forEach(d => {
      d.addEventListener("toggle", () => {
        if (!d.open) return;
        faqs.forEach(other => { if (other !== d) other.open = false; });
      });
    });

    // ちょい滑らかスクロール（対応ブラウザだけ）
    document.documentElement.style.scrollBehavior = "smooth";
  </script>
</body>
</html>
