---
title: "TuxPi"
toc: false
sidebar:
  hide: true
width: full
---

<div class="tuxpi-main-container">

    <!-- HERO SECTION -->
    <div class="tuxpi-hero">
        <div id="hero-slider" class="hero-slider">
            <div class="hero-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.7)), url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
            <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.7)), url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/proxmox-homelab.png');"></div>
        </div>
        
        <div class="hero-content">
            <h1 class="hero-title">TUX<span>PI</span></h1>
            <div class="typing-box">
                <span id="typing-text"></span><span class="cursor">_</span>
            </div>
            <div class="hero-btns">
                <a href="#articoli" class="btn-primary">Ultimi Articoli</a>
                <a href="#sezioni" class="btn-secondary">Sezioni</a>
            </div>
        </div>
        <div class="hero-fade"></div>
    </div>

    <!-- CONTENUTO PAGINA -->
    <div class="content-body">
        
        <div class="intro-section">
            <h2>🐧 Benvenuto su TuxPi</h2>
            <p>Esplora il mondo Linux, Proxmox e Raspberry Pi. Guide pratiche e approfondimenti per dominare il tuo hardware.</p>
        </div>

        <div id="sezioni" class="cards-grid">
            <a href="/docs/proxmox" class="t-card">
                <div class="t-card-img" style="background-image: url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=800');"></div>
                <div class="t-card-info"><h3>Proxmox</h3><p>Virtualizzazione estrema.</p></div>
            </a>
            <a href="/docs/raspberry-pi" class="t-card">
                <div class="t-card-img" style="background-image: url('https://images.unsplash.com/photo-1629739945244-c7821487b257?q=80&w=800');"></div>
                <div class="t-card-info"><h3>Raspberry Pi</h3><p>IoT e bassi consumi.</p></div>
            </a>
            <a href="/docs/self-hosting" class="t-card">
                <div class="t-card-img" style="background-image: url('https://images.unsplash.com/photo-1605745341112-85968b193ef5?q=80&w=800');"></div>
                <div class="t-card-info"><h3>Self-Hosting</h3><p>I tuoi dati, il tuo cloud.</p></div>
            </a>
            <a href="/docs/linux" class="t-card">
                <div class="t-card-img" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
                <div class="t-card-info"><h3>Cultura Linux</h3><p>Open Source e Terminale.</p></div>
            </a>
        </div>

        <div id="articoli" class="articles-section">
            <h2 class="section-title">Ultimi Articoli</h2>
            {{< latest-articles >}}
        </div>
    </div>
</div>

<style>
/* --- 1. BARRE DI SCORRIMENTO (APPAIONO AL PASSAGGIO) --- */
html { scrollbar-width: none; overflow-x: hidden; }
html:hover { scrollbar-width: thin; scrollbar-color: #3b82f6 transparent; }

/* Per Chrome/Safari */
body::-webkit-scrollbar { width: 8px; display: none; }
body:hover::-webkit-scrollbar { display: block; }
::-webkit-scrollbar-thumb { background: #3b82f6; border-radius: 10px; }

/* --- 2. RESET TOTALE SPAZI (NO SIDEBARS) --- */
/* Rimuove i limiti di larghezza del tema Hextra */
.hx-mx-auto.hx-flex.hx-max-w-screen-xl {
    max-width: 100% !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
}
main.hx-w-full { 
    max-width: 100% !important; 
    padding: 0 !important; 
}
/* Nasconde Table of Contents e Sidebar */
aside, .hextra-toc, .hextra-breadcrumb, h1.hx-text-4xl { display: none !important; }

/* --- 3. STILE HERO (LARGHEZZA TOTALE) --- */
.tuxpi-hero {
    position: relative; width: 100%; height: 75vh;
    background: #000; overflow: hidden; margin-top: -64px;
}
.hero-slide {
    position: absolute; inset: 0; background-size: cover; background-position: center;
    opacity: 0; transition: opacity 1s ease-in-out;
}
.hero-slide.active { opacity: 1; }
.hero-content {
    position: relative; z-index: 10; height: 100%;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    text-align: center; color: white;
}
.hero-title { font-size: clamp(3rem, 10vw, 7rem) !important; font-weight: 900 !important; margin: 0 !important; }
.hero-title span { color: #3b82f6; }
.typing-box { font-family: monospace; font-size: 1.5rem; height: 2rem; }
.hero-fade { position: absolute; bottom: 0; width: 100%; height: 150px; background: linear-gradient(transparent, #111); z-index: 5; }

/* --- 4. CORPO PAGINA (CENTRALIZZATO E LARGO) --- */
.content-body {
    max-width: 1500px; /* Qui decidi la larghezza massima del testo */
    margin: 0 auto !important; /* Centra il contenuto nel nuovo spazio 100% */
    padding: 3rem 2rem;
}

.intro-section { text-align: center; margin-bottom: 4rem; }
.intro-section h2 { font-size: 2.5rem !important; margin-bottom: 1rem !important; }

/* --- 5. GRID CARD --- */
.cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 25px;
}
.t-card {
    position: relative; height: 300px; border-radius: 20px; overflow: hidden;
    border: 1px solid rgba(255,255,255,0.1); text-decoration: none !important;
    transition: 0.3s;
}
.t-card-img { position: absolute; inset: 0; background-size: cover; background-position: center; filter: brightness(0.4); transition: 0.4s; }
.t-card-info { position: relative; z-index: 2; height: 100%; display: flex; flex-direction: column; justify-content: flex-end; padding: 20px; }
.t-card h3 { color: white !important; font-size: 1.4rem !important; margin: 0 !important; }
.t-card p { color: #aaa !important; font-size: 0.9rem !important; margin: 5px 0 0 0 !important; }

.t-card:hover { transform: translateY(-8px); border-color: #3b82f6; }
.t-card:hover .t-card-img { filter: brightness(0.6); transform: scale(1.05); }

/* BOTTONI */
.hero-btns { margin-top: 2rem; display: flex; gap: 15px; }
.btn-primary { background: #3b82f6; color: white !important; padding: 12px 25px; border-radius: 8px; font-weight: bold; text-decoration: none !important; }
.btn-secondary { border: 1px solid white; color: white !important; padding: 12px 25px; border-radius: 8px; font-weight: bold; text-decoration: none !important; }

.section-title { font-size: 2rem !important; margin-bottom: 2rem !important; border-bottom: 2px solid #3b82f6; display: inline-block; }
</style>

<script>
const phrases = ["Linux & Open Source", "Proxmox Homelab", "Raspberry Pi & IoT"];
const slides = document.querySelectorAll('.hero-slide');
const textElement = document.getElementById('typing-text');
let currentIndex = 0, charIndex = 0, isDeleting = false;

function updateSlides(index) {
    slides.forEach((slide, i) => slide.classList.toggle('active', i === index));
}

function typeEffect() {
    const currentPhrase = phrases[currentIndex];
    textElement.textContent = isDeleting ? currentPhrase.substring(0, charIndex--) : currentPhrase.substring(0, charIndex++);
    
    let speed = isDeleting ? 50 : 150;
    if (!isDeleting && charIndex > currentPhrase.length) { speed = 2000; isDeleting = true; }
    else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        currentIndex = (currentIndex + 1) % phrases.length;
        updateSlides(currentIndex);
        speed = 500;
    }
    setTimeout(typeEffect, speed);
}
document.addEventListener('DOMContentLoaded', typeEffect);
</script>
