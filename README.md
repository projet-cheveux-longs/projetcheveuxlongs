<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Projet Solid'Hair — Valorisation Capillaire</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #f4f0e6;
    --dark: #1c2e1e;
    --gold: #4a7c59;
    --warm: #2d5a3d;
    --light-brown: #2d5a3d;
    --accent: #6aab7e;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background-color: var(--cream);
    color: var(--dark);
    overflow-x: hidden;
  }

  /* Grain texture overlay */
  body::before {
    content: '';
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 9999;
    opacity: 0.4;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 3rem;
    background: rgba(244,240,230,0.95);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid rgba(74,124,89,0.2);
  }

  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    font-size: 1.1rem;
    letter-spacing: 0.05em;
    color: var(--dark);
    text-transform: uppercase;
    text-decoration: none;
  }

  .nav-logo span { color: var(--gold); }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    font-size: 0.82rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--dark);
    text-decoration: none;
    opacity: 0.7;
    transition: opacity 0.2s, color 0.2s;
  }

  .nav-links a:hover { opacity: 1; color: var(--gold); }

  /* HERO */
  #accueil {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-top: 80px;
    overflow: hidden;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 6rem 4rem 6rem 5rem;
    position: relative;
  }

  .hero-tag {
    font-size: 0.72rem;
    font-weight: 500;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }

  .hero-tag::before {
    content: '';
    width: 2rem;
    height: 1px;
    background: var(--gold);
  }

  .hero-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3.5rem, 5vw, 5.5rem);
    font-weight: 900;
    line-height: 1.0;
    color: var(--dark);
    margin-bottom: 2rem;
  }

  .hero-title em {
    font-style: italic;
    color: var(--warm);
  }

  .hero-stat {
    background: var(--dark);
    color: var(--cream);
    padding: 1.5rem 2rem;
    margin-bottom: 2.5rem;
    position: relative;
    max-width: 380px;
  }

  .hero-stat::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 4px;
    background: var(--gold);
  }

  .hero-stat .number {
    font-family: 'Playfair Display', serif;
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--gold);
    line-height: 1;
  }

  .hero-stat p {
    font-size: 0.85rem;
    opacity: 0.8;
    margin-top: 0.3rem;
    line-height: 1.5;
  }

  .hero-ctas {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn-primary {
    display: inline-block;
    background: var(--dark);
    color: var(--cream);
    padding: 1rem 2rem;
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    transition: background 0.25s, transform 0.2s;
  }

  .btn-primary:hover { background: var(--warm); transform: translateY(-2px); }

  .btn-secondary {
    display: inline-block;
    border: 1.5px solid var(--dark);
    color: var(--dark);
    padding: 1rem 2rem;
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    transition: background 0.25s, color 0.25s, transform 0.2s;
  }

  .btn-secondary:hover { background: var(--dark); color: var(--cream); transform: translateY(-2px); }

  .hero-right {
    position: relative;
    background: #1c2e1e;
    overflow: hidden;
  }

  .hero-right::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(106,171,126,0.2) 0%, rgba(28,46,30,0.8) 100%);
  }

  .hero-right-content {
    position: absolute;
    inset: 0;
    z-index: 2;
    display: flex;
    align-items: flex-end;
    padding: 3rem;
  }

  .hero-right-text {
    font-family: 'Playfair Display', serif;
    font-size: clamp(4rem, 8vw, 9rem);
    font-weight: 900;
    font-style: italic;
    color: rgba(245,240,232,0.15);
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    white-space: nowrap;
    z-index: 1;
    pointer-events: none;
  }

  .hair-visual {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2;
    position: relative;
  }

  /* SVG Hair strands */
  .hair-svg {
    width: 70%;
    height: 70%;
    opacity: 0.7;
  }

  .quote-card {
    background: rgba(245,240,232,0.95);
    padding: 1.5rem;
    max-width: 280px;
    border-left: 3px solid var(--gold);
    z-index: 3;
    position: relative;
  }

  .quote-card p {
    font-family: 'Playfair Display', serif;
    font-size: 1rem;
    font-style: italic;
    line-height: 1.5;
    color: var(--dark);
  }

  /* SECTION: POURQUOI */
  #pourquoi-meme {
    padding: 8rem 5rem;
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 6rem;
    border-top: 1px solid rgba(74,124,89,0.25);
  }

  .section-label {
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    writing-mode: vertical-rl;
    text-orientation: mixed;
    align-self: start;
    margin-top: 0.5rem;
  }

  .section-content h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 3.2rem);
    font-weight: 700;
    line-height: 1.15;
    margin-bottom: 2.5rem;
    color: var(--dark);
  }

  .section-content p {
    font-size: 1.05rem;
    line-height: 1.8;
    color: rgba(26,18,9,0.75);
    margin-bottom: 1.5rem;
    max-width: 580px;
  }

  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
    margin-top: 3rem;
  }

  .stat-card {
    padding: 2rem;
    border: 1px solid rgba(74,124,89,0.3);
    background: linear-gradient(135deg, rgba(74,124,89,0.05), rgba(74,124,89,0.12));
    transition: transform 0.2s;
  }

  .stat-card:hover { transform: translateY(-4px); }

  .stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
  }

  .stat-label {
    font-size: 0.85rem;
    margin-top: 0.5rem;
    opacity: 0.7;
    line-height: 1.5;
  }

  /* SONDAGE */
  #sondage {
    background: var(--dark);
    padding: 8rem 5rem;
    position: relative;
    overflow: hidden;
  }

  #sondage::before {
    content: 'SONDAGE';
    position: absolute;
    font-family: 'Playfair Display', serif;
    font-size: 18vw;
    font-weight: 900;
    color: rgba(74,124,89,0.07);
    right: -2vw;
    top: 50%;
    transform: translateY(-50%);
    pointer-events: none;
    line-height: 1;
  }

  .sondage-inner {
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
    position: relative;
    z-index: 1;
  }

  #sondage .hero-tag { justify-content: center; color: var(--gold); }
  #sondage .hero-tag::before { background: var(--gold); }

  #sondage h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.5rem, 4vw, 4rem);
    font-weight: 700;
    color: var(--cream);
    line-height: 1.15;
    margin-bottom: 1.5rem;
  }

  #sondage p {
    color: rgba(245,240,232,0.65);
    font-size: 1.05rem;
    line-height: 1.8;
    margin-bottom: 3rem;
    max-width: 560px;
    margin-left: auto;
    margin-right: auto;
  }

  .sondage-btns {
    display: flex;
    gap: 1.5rem;
    justify-content: center;
    flex-wrap: wrap;
  }

  .btn-gold {
    display: inline-block;
    background: var(--gold);
    color: var(--dark);
    padding: 1.1rem 2.5rem;
    font-size: 0.82rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    transition: background 0.25s, transform 0.2s;
  }

  .btn-gold:hover { background: var(--accent); transform: translateY(-2px); }

  .btn-outline-cream {
    display: inline-block;
    border: 1.5px solid rgba(245,240,232,0.4);
    color: var(--cream);
    padding: 1.1rem 2.5rem;
    font-size: 0.82rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    transition: background 0.25s, color 0.25s, transform 0.2s;
  }

  .btn-outline-cream:hover { background: var(--cream); color: var(--dark); transform: translateY(-2px); }

  /* LE FUTUR */
  #le-futur-des-cheveux {
    padding: 8rem 5rem;
    border-top: 1px solid rgba(74,124,89,0.25);
  }

  .futur-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 5rem;
  }

  .futur-header h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.2rem, 3.5vw, 3.5rem);
    font-weight: 700;
    line-height: 1.1;
    max-width: 500px;
  }

  .futur-header p {
    max-width: 300px;
    font-size: 0.9rem;
    line-height: 1.7;
    opacity: 0.65;
  }

  .cards-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 0;
  }

  .card {
    padding: 3rem 2.5rem;
    border: 1px solid rgba(74,124,89,0.2);
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
    cursor: default;
  }

  .card:hover { background: rgba(74,124,89,0.06); }

  .card-number {
    font-family: 'Playfair Display', serif;
    font-size: 5rem;
    font-weight: 900;
    color: rgba(74,124,89,0.12);
    line-height: 1;
    position: absolute;
    top: 1.5rem;
    right: 1.5rem;
  }

  .card-icon {
    font-size: 2rem;
    margin-bottom: 1.5rem;
  }

  .card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    font-weight: 700;
    line-height: 1.3;
    margin-bottom: 1rem;
    color: var(--dark);
  }

  .card p {
    font-size: 0.9rem;
    line-height: 1.7;
    opacity: 0.7;
  }

  .card-tag {
    display: inline-block;
    margin-top: 1.5rem;
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    padding: 0.35rem 0.8rem;
    border: 1px solid var(--gold);
  }

  /* CONTACT */
  #contact {
    background: linear-gradient(160deg, #1c2e1e 70%, #2d5a3d);
    padding: 8rem 5rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: start;
  }

  .contact-left h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.5rem, 4vw, 4rem);
    font-weight: 700;
    color: var(--cream);
    line-height: 1.1;
    margin-bottom: 1.5rem;
  }

  .contact-left p {
    color: rgba(245,240,232,0.6);
    font-size: 1rem;
    line-height: 1.8;
    margin-bottom: 2rem;
  }

  .contact-info {
    display: flex;
    align-items: center;
    gap: 1rem;
    color: var(--gold);
    font-size: 0.9rem;
    margin-top: 2rem;
  }

  .contact-info::before {
    content: '✉';
    font-size: 1.2rem;
  }

  .contact-info a { color: var(--gold); text-decoration: none; }
  .contact-info a:hover { text-decoration: underline; }

  form {
    display: flex;
    flex-direction: column;
    gap: 1.2rem;
  }

  .form-group {
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
  }

  label {
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(245,240,232,0.5);
  }

  input, textarea {
    background: rgba(245,240,232,0.07);
    border: 1px solid rgba(245,240,232,0.15);
    color: var(--cream);
    padding: 0.9rem 1.2rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s;
  }

  input:focus, textarea:focus { border-color: var(--gold); }
  input::placeholder, textarea::placeholder { color: rgba(245,240,232,0.25); }

  textarea { min-height: 130px; resize: vertical; }

  .btn-submit {
    background: var(--gold);
    color: var(--dark);
    border: none;
    padding: 1.1rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.82rem;
    font-weight: 600;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    cursor: pointer;
    transition: background 0.25s, transform 0.2s;
    margin-top: 0.5rem;
  }

  .btn-submit:hover { background: var(--accent); transform: translateY(-2px); }

  /* FOOTER */
  footer {
    background: #111a12;
    padding: 3rem 5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(74,124,89,0.2);
  }

  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    font-size: 1rem;
    color: var(--cream);
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }

  .footer-logo span { color: var(--gold); }

  .footer-copy {
    font-size: 0.8rem;
    color: rgba(245,240,232,0.3);
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-left > * {
    animation: fadeUp 0.8s ease forwards;
    opacity: 0;
  }

  .hero-left > *:nth-child(1) { animation-delay: 0.1s; }
  .hero-left > *:nth-child(2) { animation-delay: 0.25s; }
  .hero-left > *:nth-child(3) { animation-delay: 0.4s; }
  .hero-left > *:nth-child(4) { animation-delay: 0.55s; }

  /* Hair animated lines */
  .hair-line {
    stroke-dasharray: 600;
    stroke-dashoffset: 600;
    animation: drawHair 2.5s ease forwards;
  }

  .hair-line:nth-child(2) { animation-delay: 0.3s; }
  .hair-line:nth-child(3) { animation-delay: 0.6s; }
  .hair-line:nth-child(4) { animation-delay: 0.9s; }
  .hair-line:nth-child(5) { animation-delay: 1.2s; }
  .hair-line:nth-child(6) { animation-delay: 1.5s; }

  @keyframes drawHair {
    to { stroke-dashoffset: 0; }
  }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    #accueil { grid-template-columns: 1fr; }
    .hero-right { height: 50vh; }
    .hero-left { padding: 4rem 2rem; }
    nav { padding: 1.2rem 2rem; }
    .nav-links { gap: 1.5rem; }
    #pourquoi-meme, #le-futur-des-cheveux, #contact { padding: 5rem 2rem; }
    #sondage { padding: 5rem 2rem; }
    #pourquoi-meme { grid-template-columns: 1fr; }
    .section-label { writing-mode: horizontal-tb; }
    .cards-grid { grid-template-columns: 1fr; }
    #contact { grid-template-columns: 1fr; gap: 3rem; }
    .futur-header { flex-direction: column; gap: 1.5rem; }
    .stats-grid { grid-template-columns: 1fr; }
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
    <li><a href="#le-futur-des-cheveux">Le futur</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="accueil">
  <div class="hero-left">
    <div class="hero-tag">Projet Solid'Hair</div>
    <h1 class="hero-title">
      Les cheveux <em>valent</em> bien<br>plus que la poubelle
    </h1>
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
    <p>Le résultat : des tonnes de kératine humaine partent à la poubelle chaque semaine, alors que cette matière pourrait alimenter des perruques médicales, dépolluer des nappes phréatiques, ou s'intégrer dans des matériaux composites du futur.</p>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-number">90 000</div>
        <div class="stat-label">salons de coiffure en France concernés par cette problématique</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">~40 T</div>
        <div class="stat-label">de cheveux en moyenne par salon par an, partant à la poubelle</div>
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
    <p>Nous menons une enquête auprès du grand public et des professionnels de la coiffure. Vos réponses façonnent directement notre projet et les solutions que nous proposerons.</p>
    <div class="sondage-btns">
      <a href="https://docs.google.com/forms/d/e/1FAIpQLScTGfVct9I1TbkycjhAQgSc-bcTVCB88m1w39T8A3CYR9TUIg/viewform?usp=header" target="_blank" class="btn-gold">Sondage grand public</a>
      <a href="https://docs.google.com/forms/d/e/1FAIpQLSdBxDG2PoOh6AEapEJKPkI5h5AfAkBI6n3j2lL3539fOzXYnA/viewform?usp=dialog" target="_blank" class="btn-outline-cream">Sondage coiffeurs</a>
    </div>
  </div>
</section>

<!-- LE FUTUR -->
<section id="le-futur-des-cheveux">
  <div class="futur-header">
    <h2>Les cheveux<br>ont du <em style="font-style:italic; color:var(--warm);">talent</em></h2>
    <p>La kératine capillaire est une ressource extraordinaire. Voici les grandes directions dans lesquelles elle peut s'inscrire.</p>
  </div>
  <div class="cards-grid">
    <div class="card">
      <div class="card-number">01</div>
      <div class="card-icon">🎗️</div>
      <h3>Un enjeu humain — les perruques médicales</h3>
      <p>Des milliers de personnes atteintes de cancer ou d'alopécie voient leurs cheveux lutter contre la maladie. Les dons capillaires permettent de fabriquer des perruques de haute qualité à prix accessible.</p>
      <span class="card-tag">Solidarité</span>
    </div>
    <div class="card">
      <div class="card-number">02</div>
      <div class="card-icon">🌿</div>
      <h3>Un enjeu écologique — transformer en ressource</h3>
      <p>Les cheveux absorbent les hydrocarbures et métaux lourds. Utilisés en tresses ou en nattes, ils peuvent dépolluer des cours d'eau et des sols contaminés — une technique déjà éprouvée après des marées noires.</p>
      <span class="card-tag">Environnement</span>
    </div>
    <div class="card">
      <div class="card-number">03</div>
      <div class="card-icon">🏗️</div>
      <h3>Des freins logistiques à lever</h3>
      <p>Stocker, hygiéniser, conditionner et acheminer les cheveux vers les filières adaptées : c'est le cœur du problème que nous cherchons à résoudre avec notre réseau de collecte partenaire.</p>
      <span class="card-tag">Logistique</span>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-left">
    <div class="hero-tag" style="color:var(--gold);">Contactez-nous</div>
    <h2>Rejoignez notre aventure capillaire</h2>
    <p>Vous êtes coiffeur, association, chercheur ou simplement curieux de participer ? Nous serions ravis d'échanger avec vous sur ce projet.</p>
    <div class="contact-info">
      <a href="/cdn-cgi/l/email-protection#6515170a0f0011060d001300101d090a0b02165c54250208040c094b060a08"><span class="__cf_email__" data-cfemail="19696b76737c6d7a717c6f7c6c617576777e6a2028597e74787075377a7674">[email&#160;protected]</span></a>
    </div>
  </div>
  <div class="contact-right">
    <form onsubmit="handleSubmit(event)">
      <div class="form-group">
        <label>Votre nom</label>
        <input type="text" placeholder="Marie Dupont" required>
      </div>
      <div class="form-group">
        <label>Adresse email</label>
        <input type="email" placeholder="marie@exemple.fr" required>
      </div>
      <div class="form-group">
        <label>Téléphone (optionnel)</label>
        <input type="tel" placeholder="+33 6 12 34 56 78">
      </div>
      <div class="form-group">
        <label>Votre message</label>
        <textarea placeholder="Parlez-nous de vous et de votre intérêt pour le projet…"></textarea>
      </div>
      <button type="submit" class="btn-submit">Envoyer le message →</button>
    </form>
  </div>
</section>

<footer>
  <div class="footer-logo">Projet <span>Cheveux Longs</span></div>
  <div class="footer-copy">© 2025 Projet Cheveux Longs — Tous droits réservés</div>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('.btn-submit');
    btn.textContent = 'Message envoyé ✓';
    btn.style.background = '#4caf50';
    btn.style.color = '#fff';
    setTimeout(() => {
      btn.textContent = 'Envoyer le message →';
      btn.style.background = '';
      btn.style.color = '';
      e.target.reset();
    }, 3000);
  }

  // Scroll fade-in for sections
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });
