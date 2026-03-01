<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Projet Cheveux Longs — Valorisation Capillaire</title>
<link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'%3E%3Crect width='32' height='32' rx='8' fill='%231c2e1e'/%3E%3Cpath d='M10 4 C8 10, 14 14, 11 20 C9 25, 13 28, 12 31' stroke='%236aab7e' stroke-width='2.5' stroke-linecap='round' fill='none'/%3E%3Cpath d='M16 3 C15 9, 19 13, 17 19 C15 24, 18 27, 17 31' stroke='%23f4f0e6' stroke-width='2' stroke-linecap='round' fill='none'/%3E%3Cpath d='M22 5 C21 11, 24 15, 22 21 C21 26, 23 28, 22 31' stroke='%234a7c59' stroke-width='2' stroke-linecap='round' fill='none'/%3E%3C/svg%3E">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #f4f0e6;
    --dark: #1c2e1e;
    --gold: #4a7c59;
    --warm: #2d5a3d;
    --accent: #6aab7e;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body { font-family: 'DM Sans', sans-serif; background-color: var(--cream); color: var(--dark); overflow-x: hidden; }

  body::before {
    content: '';
    position: fixed; top: 0; left: 0; right: 0; bottom: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 9999; opacity: 0.4;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.5rem 3rem;
    background: rgba(244,240,230,0.95);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid rgba(74,124,89,0.2);
  }
  .nav-logo { font-family: 'Playfair Display', serif; font-weight: 900; font-size: 1.1rem; letter-spacing: 0.05em; color: var(--dark); text-transform: uppercase; text-decoration: none; }
  .nav-logo span { color: var(--gold); }
  .nav-links { display: flex; gap: 2rem; list-style: none; align-items: center; }
  .nav-links a { font-size: 0.82rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; color: var(--dark); text-decoration: none; opacity: 0.7; transition: opacity 0.2s, color 0.2s; }
  .nav-links a:hover { opacity: 1; color: var(--gold); }
  .nav-insta { display: flex; align-items: center; gap: 0.4rem; background: var(--dark); color: var(--cream) !important; opacity: 1 !important; padding: 0.45rem 1rem; border-radius: 2px; font-size: 0.78rem !important; transition: background 0.2s !important; }
  .nav-insta:hover { background: var(--gold) !important; color: var(--cream) !important; }
  .nav-insta svg { width: 14px; height: 14px; }

  /* HERO */
  #accueil { min-height: 100vh; display: grid; grid-template-columns: 1fr 1fr; padding-top: 80px; overflow: hidden; }
  .hero-left { display: flex; flex-direction: column; justify-content: center; padding: 6rem 4rem 6rem 5rem; }
  .hero-tag { font-size: 0.72rem; font-weight: 500; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold); margin-bottom: 1.5rem; display: flex; align-items: center; gap: 0.8rem; }
  .hero-tag::before { content: ''; width: 2rem; height: 1px; background: var(--gold); }
  .hero-title { font-family: 'Playfair Display', serif; font-size: clamp(3.5rem, 5vw, 5.5rem); font-weight: 900; line-height: 1.0; color: var(--dark); margin-bottom: 2rem; }
  .hero-title em { font-style: italic; color: var(--warm); }
  .hero-stat { background: var(--dark); color: var(--cream); padding: 1.5rem 2rem; position: relative; max-width: 380px; }
  .hero-stat::before { content: ''; position: absolute; left: 0; top: 0; bottom: 0; width: 4px; background: var(--accent); }
  .hero-stat .number { font-family: 'Playfair Display', serif; font-size: 2.2rem; font-weight: 700; color: var(--accent); line-height: 1; }
  .hero-stat p { font-size: 0.85rem; opacity: 0.8; margin-top: 0.3rem; line-height: 1.5; }

  .hero-right { position: relative; background: #1c2e1e; overflow: hidden; }
  .hero-right::after { content: ''; position: absolute; inset: 0; background: linear-gradient(135deg, rgba(106,171,126,0.2) 0%, rgba(28,46,30,0.8) 100%); }
  .hero-right-text { font-family: 'Playfair Display', serif; font-size: clamp(4rem, 8vw, 9rem); font-weight: 900; font-style: italic; color: rgba(245,240,232,0.08); position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); white-space: nowrap; z-index: 1; pointer-events: none; }
  .hair-visual { width: 100%; height: 100%; display: flex; align-items: center; justify-content: center; z-index: 2; position: relative; }
  .hair-svg { width: 70%; height: 70%; opacity: 0.7; }

  /* POURQUOI */
  #pourquoi-meme { padding: 8rem 5rem; display: grid; grid-template-columns: 1fr 2fr; gap: 6rem; border-top: 1px solid rgba(74,124,89,0.25); }
  .section-label { font-size: 0.7rem; font-weight: 500; letter-spacing: 0.25em; text-transform: uppercase; color: var(--gold); writing-mode: vertical-rl; align-self: start; margin-top: 0.5rem; }
  .section-content h2 { font-family: 'Playfair Display', serif; font-size: clamp(2rem, 3.5vw, 3.2rem); font-weight: 700; line-height: 1.15; margin-bottom: 2.5rem; }
  .section-content p { font-size: 1.05rem; line-height: 1.8; color: rgba(26,18,9,0.75); margin-bottom: 1.5rem; max-width: 580px; }
  .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 3rem; }
  .stat-card { padding: 2rem; border: 1px solid rgba(74,124,89,0.3); background: linear-gradient(135deg, rgba(74,124,89,0.05), rgba(74,124,89,0.12)); transition: transform 0.2s; }
  .stat-card:hover { transform: translateY(-4px); }
  .stat-number { font-family: 'Playfair Display', serif; font-size: 2.5rem; font-weight: 900; color: var(--gold); line-height: 1; }
  .stat-label { font-size: 0.85rem; margin-top: 0.5rem; opacity: 0.7; line-height: 1.5; }

  /* SONDAGE */
  #sondage { background: var(--dark); padding: 8rem 5rem; position: relative; overflow: hidden; }
  #sondage::before { content: 'SONDAGE'; position: absolute; font-family: 'Playfair Display', serif; font-size: 18vw; font-weight: 900; color: rgba(74,124,89,0.07); right: -2vw; top: 50%; transform: translateY(-50%); pointer-events: none; line-height: 1; }
  .sondage-inner { max-width: 800px; margin: 0 auto; text-align: center; position: relative; z-index: 1; }
  #sondage .hero-tag { justify-content: center; color: var(--accent); }
  #sondage .hero-tag::before { background: var(--accent); }
  #sondage h2 { font-family: 'Playfair Display', serif; font-size: clamp(2.5rem, 4vw, 4rem); font-weight: 700; color: var(--cream); line-height: 1.15; margin-bottom: 1.5rem; }
  #sondage p { color: rgba(245,240,232,0.65); font-size: 1.05rem; line-height: 1.8; margin-bottom: 3rem; max-width: 560px; margin-left: auto; margin-right: auto; }
  .sondage-btns { display: flex; gap: 1.5rem; justify-content: center; flex-wrap: wrap; }
  .btn-gold { display: inline-block; background: var(--gold); color: var(--cream); padding: 1.1rem 2.5rem; font-size: 0.82rem; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; text-decoration: none; transition: background 0.25s, transform 0.2s; }
  .btn-gold:hover { background: var(--accent); transform: translateY(-2px); }
  .btn-outline-cream { display: inline-block; border: 1.5px solid rgba(245,240,232,0.4); color: var(--cream); padding: 1.1rem 2.5rem; font-size: 0.82rem; font-weight: 500; letter-spacing: 0.12em; text-transform: uppercase; text-decoration: none; transition: background 0.25s, color 0.25s, transform 0.2s; }
  .btn-outline-cream:hover { background: var(--cream); color: var(--dark); transform: translateY(-2px); }

  /* ENJEUX — CARDS */
  #le-futur-des-cheveux { padding: 8rem 5rem; border-top: 1px solid rgba(74,124,89,0.25); }
  .futur-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 5rem; }
  .futur-header h2 { font-family: 'Playfair Display', serif; font-size: clamp(2.2rem, 3.5vw, 3.5rem); font-weight: 700; line-height: 1.1; max-width: 500px; }
  .futur-header p { max-width: 300px; font-size: 0.9rem; line-height: 1.7; opacity: 0.65; }
  .cards-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; }

  .card { padding: 3rem 2.5rem; border: 1px solid rgba(74,124,89,0.2); position: relative; overflow: hidden; transition: background 0.3s; cursor: pointer; }
  .card:hover { background: rgba(74,124,89,0.06); }
  .card.open { background: rgba(74,124,89,0.09); }
  .card-number { font-family: 'Playfair Display', serif; font-size: 5rem; font-weight: 900; color: rgba(74,124,89,0.12); line-height: 1; position: absolute; top: 1.5rem; right: 1.5rem; }
  .card-icon { font-size: 2rem; margin-bottom: 1.5rem; }
  .card h3 { font-family: 'Playfair Display', serif; font-size: 1.3rem; font-weight: 700; line-height: 1.3; margin-bottom: 1rem; color: var(--dark); }
  .card > p { font-size: 0.9rem; line-height: 1.7; opacity: 0.7; }
  .card-tag { display: inline-block; margin-top: 1.5rem; font-size: 0.7rem; font-weight: 500; letter-spacing: 0.15em; text-transform: uppercase; color: var(--gold); padding: 0.35rem 0.8rem; border: 1px solid var(--gold); }
  .card-toggle { display: flex; align-items: center; gap: 0.5rem; margin-top: 1.2rem; font-size: 0.72rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: var(--gold); }
  .card-toggle .arrow { transition: transform 0.35s ease; }
  .card.open .card-toggle .arrow { transform: rotate(180deg); }
  .card-details { max-height: 0; overflow: hidden; opacity: 0; transition: max-height 0.6s ease, opacity 0.4s ease; }
  .card.open .card-details { max-height: 1200px; opacity: 1; padding-top: 1.5rem; border-top: 1px solid rgba(74,124,89,0.2); margin-top: 1.5rem; }
  .card-details p { font-size: 0.88rem; line-height: 1.8; opacity: 0.8; margin-bottom: 1rem; }
  .card-details h4 { font-family: 'Playfair Display', serif; font-size: 0.95rem; font-weight: 700; color: var(--gold); margin: 1.2rem 0 0.6rem; }
  .card-details ul { list-style: none; display: flex; flex-direction: column; gap: 0.5rem; margin-bottom: 0.8rem; }
  .card-details li { font-size: 0.84rem; line-height: 1.6; opacity: 0.75; padding-left: 1.2rem; position: relative; }
  .card-details li::before { content: '→'; position: absolute; left: 0; color: var(--gold); }

  /* SECTION : CE QU'ON A FAIT */
  #notre-histoire {
    padding: 8rem 5rem;
    background: var(--dark);
    border-top: 1px solid rgba(74,124,89,0.25);
    position: relative;
    overflow: hidden;
  }
  #notre-histoire::before {
    content: '2025';
    position: absolute;
    font-family: 'Playfair Display', serif;
    font-size: 20vw;
    font-weight: 900;
    color: rgba(74,124,89,0.05);
    right: -1vw;
    bottom: -2rem;
    pointer-events: none;
    line-height: 1;
  }
  .histoire-inner { position: relative; z-index: 1; }
  .histoire-header { margin-bottom: 5rem; }
  .histoire-header .hero-tag { color: var(--accent); }
  .histoire-header .hero-tag::before { background: var(--accent); }
  .histoire-header h2 { font-family: 'Playfair Display', serif; font-size: clamp(2.2rem, 3.5vw, 3.5rem); font-weight: 700; color: var(--cream); line-height: 1.1; margin-top: 1rem; }

  .histoire-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; }

  .histoire-col h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--accent);
    margin-bottom: 2rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid rgba(106,171,126,0.25);
  }

  .timeline { display: flex; flex-direction: column; gap: 2rem; }
  .timeline-item { display: flex; gap: 1.5rem; align-items: flex-start; }
  .timeline-dot {
    width: 36px;
    height: 36px;
    min-width: 36px;
    background: rgba(74,124,89,0.2);
    border: 1.5px solid var(--gold);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1rem;
    margin-top: 0.1rem;
  }
  .timeline-content {}
  .timeline-date { font-size: 0.7rem; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: var(--accent); margin-bottom: 0.3rem; }
  .timeline-title { font-family: 'Playfair Display', serif; font-size: 1.05rem; font-weight: 700; color: var(--cream); margin-bottom: 0.4rem; line-height: 1.3; }
  .timeline-desc { font-size: 0.87rem; line-height: 1.7; color: rgba(245,240,232,0.6); }

  .projets-list { display: flex; flex-direction: column; gap: 1.5rem; }
  .projet-item {
    padding: 1.5rem;
    border: 1px solid rgba(74,124,89,0.25);
    background: rgba(74,124,89,0.06);
    position: relative;
    transition: background 0.2s;
  }
  .projet-item:hover { background: rgba(74,124,89,0.12); }
  .projet-item::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 3px;
    background: var(--accent);
  }
  .projet-label { font-size: 0.68rem; font-weight: 600; letter-spacing: 0.18em; text-transform: uppercase; color: var(--accent); margin-bottom: 0.4rem; }
  .projet-title { font-family: 'Playfair Display', serif; font-size: 1rem; font-weight: 700; color: var(--cream); margin-bottom: 0.4rem; }
  .projet-desc { font-size: 0.85rem; line-height: 1.7; color: rgba(245,240,232,0.6); }

  /* CONTACT */
  #contact {
    background: linear-gradient(160deg, #1c2e1e 70%, #2d5a3d);
    padding: 8rem 5rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 2rem;
  }
  .contact-left .hero-tag { justify-content: center; color: var(--accent); }
  .contact-left h2 { font-family: 'Playfair Display', serif; font-size: clamp(2.5rem, 4vw, 4rem); font-weight: 700; color: var(--cream); line-height: 1.1; margin-bottom: 1.5rem; }
  .contact-left p { color: rgba(245,240,232,0.6); font-size: 1rem; line-height: 1.8; max-width: 560px; }
  .contact-links { display: flex; gap: 1.5rem; justify-content: center; flex-wrap: wrap; margin-top: 1.5rem; }
  .contact-link { display: inline-flex; align-items: center; gap: 0.6rem; color: var(--accent); font-size: 0.95rem; font-weight: 500; text-decoration: none; padding: 0.8rem 1.5rem; border: 1px solid rgba(106,171,126,0.35); transition: background 0.2s, color 0.2s; }
  .contact-link:hover { background: rgba(106,171,126,0.15); }
  .contact-link svg { width: 18px; height: 18px; }

  /* FOOTER */
  footer { background: #111a12; padding: 3rem 5rem; display: flex; justify-content: space-between; align-items: center; border-top: 1px solid rgba(74,124,89,0.2); flex-wrap: wrap; gap: 1rem; }
  .footer-logo { font-family: 'Playfair Display', serif; font-weight: 900; font-size: 1rem; color: var(--cream); letter-spacing: 0.05em; text-transform: uppercase; }
  .footer-logo span { color: var(--gold); }
  .footer-insta { display: flex; align-items: center; gap: 0.5rem; color: rgba(245,240,232,0.5); font-size: 0.82rem; text-decoration: none; transition: color 0.2s; }
  .footer-insta:hover { color: var(--accent); }
  .footer-insta svg { width: 16px; height: 16px; }
  .footer-copy { font-size: 0.8rem; color: rgba(245,240,232,0.3); }

  /* ANIMATIONS */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }
  .hero-left > * { animation: fadeUp 0.8s ease forwards; opacity: 0; }
  .hero-left > *:nth-child(1) { animation-delay: 0.1s; }
  .hero-left > *:nth-child(2) { animation-delay: 0.25s; }
  .hero-left > *:nth-child(3) { animation-delay: 0.4s; }
  .hair-line { stroke-dasharray: 600; stroke-dashoffset: 600; animation: drawHair 2.5s ease forwards; }
  .hair-line:nth-child(2) { animation-delay: 0.3s; }
  .hair-line:nth-child(3) { animation-delay: 0.6s; }
  .hair-line:nth-child(4) { animation-delay: 0.9s; }
  .hair-line:nth-child(5) { animation-delay: 1.2s; }
  .hair-line:nth-child(6) { animation-delay: 1.5s; }
  @keyframes drawHair { to { stroke-dashoffset: 0; } }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    #accueil { grid-template-columns: 1fr; }
    .hero-right { height: 50vh; }
    .hero-left { padding: 4rem 2rem; }
    nav { padding: 1.2rem 2rem; }
    .nav-links { gap: 1rem; }
    #pourquoi-meme, #le-futur-des-cheveux, #contact, #notre-histoire { padding: 5rem 2rem; }
    #sondage { padding: 5rem 2rem; }
    #pourquoi-meme { grid-template-columns: 1fr; }
    .section-label { writing-mode: horizontal-tb; }
    .cards-grid { grid-template-columns: 1fr; }
    .futur-header { flex-direction: column; gap: 1.5rem; }
    .stats-grid { grid-template-columns: 1fr; }
    .histoire-grid { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 1rem; text-align: center; }
  }
</style>
</head>
<body>

<nav>
  <a href="#accueil" class="nav-logo">Projet <span>Cheveux Longs</span></a>
  <ul class="nav-links">
    <li><a href="#accueil">Accueil</a></li>
    <li><a href="#pourquoi-meme">Pourquoi</a></li>
    <li><a href="#sondage">Sondage</a></li>
    <li><a href="#le-futur-des-cheveux">Les enjeux</a></li>
    <li><a href="#notre-histoire">Notre parcours</a></li>
    <li><a href="#contact">Contact</a></li>
    <li>
      <a href="https://www.instagram.com/projet_cheveux_longs" target="_blank" class="nav-insta">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
        Instagram
      </a>
    </li>
  </ul>
</nav>

<!-- HERO -->
<section id="accueil">
  <div class="hero-left">
    <div class="hero-tag">Projet Cheveux Longs</div>
    <h1 class="hero-title">Les cheveux <em>valent</em> bien<br>plus que la poubelle</h1>
    <div class="hero-stat">
      <div class="number">3 000–4 000 T</div>
      <p>de cheveux jetés chaque année en France par 90 000 salons — alors qu'ils pourraient être valorisés.</p>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-right-text">Cheveux</div>
    <div class="hair-visual">
      <svg class="hair-svg" viewBox="0 0 300 400" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path class="hair-line" d="M 80 20 C 60 80, 120 120, 90 180 C 70 230, 110 270, 85 340 C 75 360, 80 385, 85 400" stroke="rgba(244,240,230,0.55)" stroke-width="2.5" stroke-linecap="round"/>
        <path class="hair-line" d="M 120 10 C 140 70, 100 110, 130 165 C 155 215, 125 265, 140 330 C 148 360, 145 385, 140 400" stroke="rgba(106,171,126,0.85)" stroke-width="2" stroke-linecap="round"/>
        <path class="hair-line" d="M 160 5 C 175 65, 145 105, 165 160 C 185 215, 160 265, 175 330 C 182 360, 178 382, 175 400" stroke="rgba(244,240,230,0.4)" stroke-width="3" stroke-linecap="round"/>
        <path class="hair-line" d="M 200 15 C 210 75, 180 115, 205 170 C 225 220, 200 268, 215 330 C 222 358, 218 382, 215 400" stroke="rgba(106,171,126,0.6)" stroke-width="2" stroke-linecap="round"/>
        <path class="hair-line" d="M 240 25 C 245 85, 215 120, 240 175 C 260 225, 235 272, 250 335 C 257 360, 253 383, 250 400" stroke="rgba(244,240,230,0.35)" stroke-width="1.5" stroke-linecap="round"/>
        <path class="hair-line" d="M 60 40 C 50 95, 85 140, 65 195 C 50 240, 75 280, 60 345 C 54 368, 57 385, 60 400" stroke="rgba(74,124,89,0.7)" stroke-width="2" stroke-linecap="round"/>
      </svg>
    </div>
  </div>
</section>

<!-- POURQUOI -->
<section id="pourquoi-meme">
  <div class="section-label">Le problème</div>
  <div class="section-content">
    <h2>Pourquoi les coiffeurs jettent encore, malgré eux ?</h2>
    <p>Aujourd'hui, le don de cheveux reste difficile pour les professionnels de la coiffure — non par manque de volonté, mais par manque de solutions concrètes de <strong>stockage</strong> et de <strong>collecte</strong> accessibles à leur échelle.</p>
    <p>Le résultat : des tonnes de kératine partent à la poubelle chaque semaine, alors que cette matière pourrait alimenter des perruques médicales, dépolluer des nappes phréatiques, ou s'intégrer dans des matériaux composites du futur.</p>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-number">90 000</div>
        <div class="stat-label">salons de coiffure en France concernés par cette problématique</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">∞</div>
        <div class="stat-label">les usages possibles — perruques, dépollution, matériaux biosourcés…</div>
      </div>
    </div>
  </div>
</section>

<!-- SONDAGE -->
<section id="sondage">
  <div class="sondage-inner">
    <div class="hero-tag">Participez</div>
    <h2>Aidez-nous à construire la solution</h2>
    <p>Nous menons une enquête auprès du grand public et des professionnels de la coiffure. Vos réponses façonnent directement notre projet.</p>
    <div class="sondage-btns">
      <a href="https://docs.google.com/forms/d/e/1FAIpQLScTGfVct9I1TbkycjhAQgSc-bcTVCB88m1w39T8A3CYR9TUIg/viewform?usp=header" target="_blank" class="btn-gold">Sondage grand public</a>
      <a href="https://docs.google.com/forms/d/e/1FAIpQLSdBxDG2PoOh6AEapEJKPkI5h5AfAkBI6n3j2lL3539fOzXYnA/viewform?usp=dialog" target="_blank" class="btn-outline-cream">Sondage coiffeurs</a>
    </div>
  </div>
</section>

<!-- LES ENJEUX -->
<section id="le-futur-des-cheveux">
  <div class="futur-header">
    <h2>Les cheveux<br>ont du <em style="font-style:italic; color:var(--warm);">talent</em></h2>
    <p>La kératine capillaire est une ressource extraordinaire. Cliquez sur chaque carte pour en savoir plus.</p>
  </div>
  <div class="cards-grid">

    <!-- SOLIDARITÉ -->
    <div class="card" onclick="toggleCard(this)">
      <div class="card-number">01</div>
      <div class="card-icon">🎗️</div>
      <h3>Un enjeu humain — les perruques</h3>
      <p>Lutter contre les effets visibles de la maladie et préserver la dignité des patients.</p>
      <span class="card-tag">Solidarité</span>
      <div class="card-toggle">En savoir plus <span class="arrow">▾</span></div>
      <div class="card-details">
        <p>En France, environ 372 500 personnes ont reçu une chimiothérapie en 2022. En moyenne, 65 % d'entre elles présentent une alopécie induite par ce traitement, soit environ <strong>240 000 patients par an</strong> souffrant d'une chute de cheveux liée à un traitement anticancéreux.</p>
        <p>D'autres formes d'alopécie surviennent également pour des raisons médicales : maladies auto-immunes (alopécie areata), troubles hormonaux, pathologies dermatologiques ou affections génétiques.</p>
        <p>La perte de cheveux dépasse largement la simple dimension esthétique. Les cheveux participent à l'identité personnelle, à l'image de soi et à l'inscription sociale. Leur chute brutale constitue une épreuve psychologique majeure : elle rend la maladie visible, peut exposer à des regards ou une stigmatisation implicite. L'accès à des prothèses capillaires de qualité contribue à alléger cette charge morale et à maintenir la dignité des patients.</p>
        <ul>
          <li>Les cheveux doivent mesurer au minimum 25 à 30 cm pour être utilisables</li>
          <li>Solid'Hair collecte les dons à partir de 25 cm, Fake Hair Don't Care à partir de 10 cm</li>
          <li>Un seul don peut permettre de confectionner une perruque entière</li>
        </ul>
      </div>
    </div>

    <!-- ENVIRONNEMENT -->
    <div class="card" onclick="toggleCard(this)">
      <div class="card-number">02</div>
      <div class="card-icon">🌿</div>
      <h3>Un enjeu écologique — transformer en ressource</h3>
      <p>Les cheveux peuvent devenir un matériau de dépollution, d'isolation et de fertilisation.</p>
      <span class="card-tag">Environnement</span>
      <div class="card-toggle">En savoir plus <span class="arrow">▾</span></div>
      <div class="card-details">
        <h4>🌊 Dépollution des eaux</h4>
        <p>Grâce à sa structure kératinée microporeuse, le cheveu peut absorber entre 3 et 9 fois son poids en hydrocarbures. Transformés en boudins ou tapis filtrants, ils sont réutilisables, lavables, biodégradables et plus efficaces que certains équivalents synthétiques.</p>
        <ul>
          <li>Lutte contre les marées noires et rejets industriels</li>
          <li>Traitement des pollutions urbaines des eaux pluviales</li>
          <li>L'association Matter of Trust utilise cette technique depuis les années 2000</li>
        </ul>
        <h4>🏠 Isolation thermique et phonique</h4>
        <p>Compactés en panneaux fibreux, les cheveux offrent des propriétés thermiques naturelles, une excellente absorption acoustique et un caractère biodégradable — alternative écologique à la laine de roche ou aux mousses synthétiques.</p>
        <h4>🌱 Agriculture et paillage</h4>
        <p>Transformés en tapis de paillage 100 % biodégradables, ils réduisent l'évaporation, limitent les mauvaises herbes et fertilisent les sols. Naturellement riches en azote, soufre et carbone, ils constituent un complément intéressant au compost.</p>
        <h4>🔬 Recherche biomédicale</h4>
        <p>La kératine extraite des cheveux est explorée pour des pansements bioactifs, des matrices de reconstruction tissulaire et des applications dermatologiques réparatrices.</p>
      </div>
    </div>

    <!-- LOGISTIQUE -->
    <div class="card" onclick="toggleCard(this)">
      <div class="card-number">03</div>
      <div class="card-icon">🏗️</div>
      <h3>Des freins logistiques à lever</h3>
      <p>Stocker, hygiéniser et acheminer les cheveux vers les filières adaptées : c'est le cœur du problème.</p>
      <span class="card-tag">Logistique</span>
      <div class="card-toggle">En savoir plus <span class="arrow">▾</span></div>
      <div class="card-details">
        <h4>📦 Des contraintes de stockage réelles</h4>
        <p>La collecte nécessite des cheveux secs, propres, attachés et conditionnés. Cela implique un tri régulier, un espace dédié et des conditions d'hygiène adaptées. Or, la majorité des salons disposent d'espaces restreints, optimisés pour l'accueil client. Toute contrainte supplémentaire devient un frein opérationnel.</p>
        <h4>📍 Un manque de points de collecte locaux</h4>
        <p>Dans de nombreuses régions, les salons doivent expédier eux-mêmes les cheveux, assumer les frais postaux et gérer le conditionnement — un coût non négligeable, notamment pour les petites structures indépendantes.</p>
        <ul>
          <li>Moins de 5 % des salons français ont accès à un système de collecte organisé</li>
          <li>La société Capillum propose un service clé en main entre 55 et 149 € HT/an</li>
          <li>Ce coût reste un frein pour les salons indépendants en contexte d'inflation des charges</li>
          <li>Notre objectif : une collecte gratuite, mensuelle, sans contrainte pour le coiffeur</li>
        </ul>
      </div>
    </div>

  </div>
</section>

<!-- NOTRE PARCOURS -->
<section id="notre-histoire">
  <div class="histoire-inner">
    <div class="histoire-header">
      <div class="hero-tag">Notre aventure</div>
      <h2>Ce qu'on a fait,<br>ce qu'on <em style="font-style:italic; color:var(--accent);">prépare</em></h2>
    </div>
    <div class="histoire-grid">

      <!-- CE QU'ON A FAIT -->
      <div class="histoire-col">
        <h3>✅ Ce qu'on a accompli</h3>
        <div class="timeline">
          <div class="timeline-item">
            <div class="timeline-dot">✂️</div>
            <div class="timeline-content">
              <div class="timeline-date">27 septembre 2025</div>
              <div class="timeline-title">Événement collecte de cheveux — Lumen, Paris-Saclay</div>
              <div class="timeline-desc">Notre premier événement de collecte capillaire, organisé au Lumen sur le campus de Paris-Saclay. Une première étape concrète pour sensibiliser et agir.</div>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot">📋</div>
            <div class="timeline-content">
              <div class="timeline-date">2025</div>
              <div class="timeline-title">Lancement des sondages</div>
              <div class="timeline-desc">Mise en ligne de deux sondages — grand public et coiffeurs — pour cartographier les besoins et comprendre les freins à la collecte.</div>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot">🌐</div>
            <div class="timeline-content">
              <div class="timeline-date">2025</div>
              <div class="timeline-title">Création du site et du compte Instagram</div>
              <div class="timeline-desc">Lancement de notre présence en ligne pour faire connaître le projet et fédérer une communauté autour de la valorisation capillaire.</div>
            </div>
          </div>
        </div>
      </div>

      <!-- CE QU'ON PRÉPARE -->
      <div class="histoire-col">
        <h3>🚀 Ce qu'on prépare</h3>
        <div class="projets-list">
          <div class="projet-item">
            <div class="projet-label">À venir</div>
            <div class="projet-title">Développement d'un réseau de collecte</div>
            <div class="projet-desc">Identifier et fédérer des salons de coiffure partenaires prêts à s'engager dans une démarche de collecte régulière, gratuite et sans contrainte.</div>
          </div>
          <div class="projet-item">
            <div class="projet-label">À venir</div>
            <div class="projet-title">Partenariats avec des associations</div>
            <div class="projet-desc">Nouer des liens avec des associations de don de cheveux et des filières de valorisation pour créer une chaîne complète de la coupe au réemploi.</div>
          </div>
          <div class="projet-item">
            <div class="projet-label">À venir</div>
            <div class="projet-title">Nouveaux événements de sensibilisation</div>
            <div class="projet-desc">Organiser d'autres collectes et temps de rencontre pour élargir l'impact du projet et toucher un public plus large.</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-left">
    <div class="hero-tag">Contactez-nous</div>
    <h2>Rejoignez notre aventure capillaire</h2>
    <p>Vous êtes coiffeur, association, chercheur ou simplement curieux de participer ? Nous serions ravis d'échanger avec vous.</p>
    <div class="contact-links">
      <a href="mailto:projetcheveuxlongs91@gmail.com" class="contact-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
        projetcheveuxlongs91@gmail.com
      </a>
      <a href="https://www.instagram.com/projet_cheveux_longs" target="_blank" class="contact-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
        @projet_cheveux_longs
      </a>
    </div>
  </div>
</section>

<footer>
  <div class="footer-logo">Projet <span>Cheveux Longs</span></div>
  <a href="https://www.instagram.com/projet_cheveux_longs" target="_blank" class="footer-insta">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
    @projet_cheveux_longs
  </a>
  <div class="footer-copy">© 2025 Projet Cheveux Longs — Tous droits réservés</div>
</footer>

<script>
  function toggleCard(card) {
    card.classList.toggle('open');
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.card, .stat-card, .timeline-item, .projet-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
