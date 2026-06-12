---
title: "TuxPi"
toc: false
sidebar:
  hide: true
width: full
---

<div class="tuxpi-hero-container">
    <div id="hero-slider" class="hero-slider">
        <div class="hero-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/proxmox-homelab.png');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
    </div>
    <div class="hero-overlay">
        <div class="hero-content">
            <h1 class="hero-title">TUX<span>PI</span></h1>
            <div class="typing-container">
                <span class="prefix">> </span>
                <span id="typing-text"></span>
                <span class="cursor">_</span>
            </div>
            <div class="hero-buttons">
                <a href="#articoli" class="btn btn-blue">Ultimi Articoli</a>
                <a href="#sezioni" class="btn btn-outline">Sezioni</a>
            </div>
        </div>
    </div>
    <div class="hero-bottom-gradient"></div>
</div>

<div class="home-content-wrapper">

    <div class="intro-box">
        <h2 class="intro-title">🐧 Benvenuto su TuxPi</h2>
        <p class="intro-text">
            In questo blog si parla di tecnologia legata al mondo <strong>Linux</strong>, con un’attenzione particolare ai vantaggi che il sistema operativo del pinguino offre rispetto ad altri ambienti. Troverai articoli di approfondimento, guide pratiche e recensioni su distribuzioni, software open source e soluzioni per ottimizzare l’esperienza d’uso.
        </p>
    </div>

    <div id="sezioni" class="section-container">
        <div class="section-header">
            <span class="section-tag">Esplora l'ecosistema</span>
            <h2 class="section-title">Domina il tuo Hardware</h2>
        </div>

        <div class="tuxpi-cards-grid">
            <a href="/docs/proxmox" class="tux-card">
                <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=800');"></div>
                <div class="card-content">
                    <div class="card-icon">🖥️</div>
                    <h3>Proxmox Lab</h3>
                    <p>Virtualizzazione estrema. Gestisci i tuoi nodi e crea un datacenter professionale.</p>
                </div>
            </a>

            <a href="/docs/raspberry-pi" class="tux-card">
                <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1629739945244-c7821487b257?q=80&w=800');"></div>
                <div class="card-content">
                    <div class="card-icon">🥧</div>
                    <h3>Mondo Raspberry</h3>
                    <p>Dallo sviluppo IoT ai server a basso consumo. Progetti pratici per la single-board.</p>
                </div>
            </a>

            <a href="/docs/self-hosting" class="tux-card">
                <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1605745341112-85968b193ef5?q=80&w=800');"></div>
                <div class="card-content">
                    <div class="card-icon">🐳</div>
                    <h3>Self-Hosting</h3>
                    <p>Docker e servizi Cloud privati. Prendi il controllo dei tuoi dati senza intermediari.</p>
                </div>
            </a>

            <a href="/docs/linux" class="tux-card">
                <div class="card-bg" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
                <div class="card-content">
                    <div class="card-icon">🐧</div>
                    <h3>Cultura Linux</h3>
                    <p>Filosofia Open Source, guide al terminale e recensioni delle migliori distribuzioni.</p>
                </div>
            </a>
        </div>
    </div>

    <div id="articoli" class="section-container">
        <div class="section-header">
            <span class="section-tag">News</span>
            <h2 class="section-title">Ultimi Articoli</h2>
        </div>
        <div class="latest-articles-wrapper">
            {{< latest-articles >}}
        </div>
    </div>

</div>

<script>
const phrases = ["Linux & Open Source", "Proxmox Homelab", "Raspberry Pi & IoT"];
const slides = document.querySelectorAll('.hero-slide');
const textElement = document.getElementById('typing-text');
let currentIndex = 0, charIndex = 0, isDeleting = false, typeSpeed = 100;

function updateSlides(index) {
    slides.forEach((slide, i) => { slide.classList.toggle('active', i === index); });
}

function typeEffect() {
    const currentPhrase = phrases[currentIndex];
    if (isDeleting) {
        textElement.textContent = currentPhrase.substring(0, charIndex - 1);
        charIndex--; typeSpeed = 40; 
    } else {
        textElement.textContent = currentPhrase.substring(0, charIndex + 1);
        charIndex++; typeSpeed = 120;
    }
    if (!isDeleting && charIndex === currentPhrase.length) {
        isDeleting = true; typeSpeed = 3000; 
    } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        currentIndex = (currentIndex + 1) % phrases.length;
        updateSlides(currentIndex);
        typeSpeed = 500; 
    }
    setTimeout(typeEffect, typeSpeed);
}
document.addEventListener('DOMContentLoaded', typeEffect);
</script>

<style>
/* --- 1. AZZERAMENTO BARRE SCORRIMENTO --- */
html, body { scrollbar-width: none; -ms-overflow-style: none; overflow-x: hidden; }
body::-webkit-scrollbar { display: none; }

/* --- 2. RIMOZIONE SPAZIO BIANCO LATERALE (FORCE FULL WIDTH) --- */
/* Questo rompe i limiti del tema Hextra e allarga tutto */
.hx-mx-auto.hx-flex.hx-max-w-screen-xl {
    max-width: 100% !important;
    width: 100% !important;
    padding: 0 !important;
    margin: 0 !important;
}

main.hx-w-full {
    max-width: 100% !important;
    width: 100% !important;
}

/* Nasconde sidebar e TOC che creano vuoti laterali */
aside, .hextra-toc, .hx-hidden.xl\:hx-block { display: none !important; }

/* --- 3. PULIZIA TEMA --- */
.hextra-breadcrumb, nav[aria-label="breadcrumb"], .hx-mt-2.hx-mb-6, h1.hx-text-4xl, hr, [class*="border-neutral"] { 
    display: none !important; 
}

/* --- 4. HERO SECTION (FULL WIDTH) --- */
.tuxpi-hero-container { 
    position: relative; width: 100vw; height: 85vh; 
    margin-top: -3.5rem; overflow: hidden; background: #000; 
}
.hero-slide { position: absolute; inset: 0; background-size: cover; background-position: center; opacity: 0; transform: scale(1.1); transition: opacity 1.5s ease, transform 10s linear; }
.hero-slide.active { opacity: 1; transform: scale(1); z-index: 2; }
.hero-overlay { position: relative; z-index: 10; height: 100%; display: flex; align-items: center; justify-content: center; background: rgba(0,0,0,0.4); }
.hero-bottom-gradient { position: absolute; bottom: 0; width: 100%; height: 200px; background: linear-gradient(to top, #111 0%, transparent 100%); z-index: 11; }

.hero-title { font-size: clamp(3.5rem, 15vw, 9rem) !important; font-weight: 900 !important; color: white !important; letter-spacing: -5px; }
.hero-title span { color: #3b82f6; }

.typing-container { font-family: 'JetBrains Mono', monospace; font-size: clamp(1rem, 3vw, 1.8rem); color: #cbd5e1; text-align: center; }
.cursor { animation: blink 0.8s infinite; color: #3b82f6; }
@keyframes blink { 50% { opacity: 0; } }

.hero-buttons { margin-top: 2rem; display: flex; gap: 15px; justify-content: center; }
.btn { padding: 12px 25px; border-radius: 10px; font-weight: bold; text-decoration: none !important; transition: 0.3s; font-size: 0.8rem; }
.btn-blue { background: #3b82f6; color: white !important; }
.btn-outline { border: 1px solid white; color: white !important; }

/* --- 5. CONTENUTO CENTRALE (AMPIO) --- */
.home-content-wrapper { 
    max-width: 1400px; /* Qui puoi aumentare a 1600px se lo vuoi ancora più largo */
    width: 90%; 
    margin: 0 auto; 
    padding: 4rem 0;
}

.intro-box { text-align: center; margin-bottom: 4rem; }
.intro-title { font-size: 2.5rem !important; color: white !important; margin-bottom: 1rem !important; }
.intro-text { font-size: 1.2rem; color: #94a3b8; line-height: 1.7; }

/* --- 6. GRID E CARD --- */
.tuxpi-cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 25px;
}
.tux-card {
    position: relative; height: 320px; border-radius: 20px; overflow: hidden;
    display: flex; align-items: flex-end; text-decoration: none !important;
    border: 1px solid rgba(255, 255, 255, 0.1) !important;
    transition: 0.4s ease;
}
.card-bg { position: absolute; inset: 0; background-size: cover; background-position: center; filter: brightness(0.4); transition: 0.5s; }
.card-content { position: relative; z-index: 2; padding: 25px; width: 100%; background: linear-gradient(to top, black, transparent); }
.card-icon { font-size: 2rem; margin-bottom: 10px; }
.tux-card h3 { color: white !important; font-size: 1.4rem !important; margin-bottom: 5px !important; }
.tux-card p { color: #94a3b8 !important; font-size: 0.9rem !important; }

.tux-card:hover { transform: translateY(-10px); border-color: #3b82f6 !important; }
.tux-card:hover .card-bg { filter: brightness(0.6) scale(1.05); }

@media (max-width: 768px) {
    .hero-buttons { flex-direction: column; align-items: center; }
    .btn { width: 80%; text-align: center; }
}
</style>
