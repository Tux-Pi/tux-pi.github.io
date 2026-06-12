---
title: "TuxPi"
toc: false
sidebar:
  hide: true
width: full
---

<style>
/* --- 1. RESET TOTALE PER LARGHEZZA INFINITA --- */
/* Rimuove i blocchi del tema Hextra che stringono la pagina e creano spazio a sinistra */
.hx-mx-auto.hx-flex.hx-max-w-screen-xl {
    max-width: 100% !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
    display: block !important;
}
main.hx-w-full {
    max-width: 100% !important;
    width: 100% !important;
}
/* Nasconde elementi superflui del tema */
aside, .hextra-toc, .hextra-breadcrumb, h1.hx-text-4xl, .hx-mb-6 { display: none !important; }

/* --- 2. BARRE DI SCORRIMENTO (APPAIONO SOLO IN HOVER) --- */
html {
    scrollbar-width: none; /* Firefox */
    -ms-overflow-style: none; /* IE/Edge */
    overflow-x: hidden;
}
/* Per Chrome, Safari e Edge */
body::-webkit-scrollbar {
    width: 8px;
}
body::-webkit-scrollbar-track { background: transparent; }
body::-webkit-scrollbar-thumb { 
    background: transparent; 
    border-radius: 10px;
}
/* Quando il mouse si muove sulla pagina, la barra appare */
body:hover::-webkit-scrollbar-thumb {
    background: rgba(59, 130, 246, 0.5); /* Blu TuxPi semitrasparente */
}
body:hover::-webkit-scrollbar-thumb:hover {
    background: rgba(59, 130, 246, 0.8);
}

/* --- 3. SLIDER FULL-WIDTH (TUTTO LO SPAZIO ORIZZONTALE) --- */
.hero-slider-container {
    position: relative;
    width: 100vw; /* Occupa tutta la larghezza del monitor */
    height: 80vh;
    left: 50%;
    transform: translateX(-50%); /* Trucco CSS per centrare un elemento 100vw */
    background: #000;
    overflow: hidden;
    margin-top: -64px; /* Compensa l'altezza della navbar */
}
.hero-slide {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    opacity: 0;
    transition: opacity 1.5s ease-in-out;
}
.hero-slide.active { opacity: 1; z-index: 1; }
.hero-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to bottom, rgba(0,0,0,0.3) 0%, rgba(17,17,17,1) 100%);
    z-index: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
}
.hero-title {
    font-size: clamp(4rem, 15vw, 9rem) !important;
    font-weight: 900 !important;
    color: white !important;
    margin: 0 !important;
    letter-spacing: -6px;
    text-transform: uppercase;
}
.hero-title span { color: #3b82f6; }
.typing-wrap {
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(1rem, 3vw, 1.8rem);
    color: #cbd5e1;
    margin-top: 10px;
    min-height: 1.5em;
}

/* --- 4. BENVENUTO E CONTENUTO --- */
.content-section {
    max-width: 1100px; /* Testo leggibile, non troppo disperso */
    margin: 0 auto;
    padding: 5rem 2rem;
    color: #e2e8f0;
}
.intro-box {
    text-align: center;
    margin-bottom: 5rem;
}
.intro-box h2 {
    font-size: 2.8rem !important;
    font-weight: 800 !important;
    color: white !important;
    margin-bottom: 1.5rem !important;
}
.intro-box p {
    font-size: 1.2rem;
    line-height: 1.8;
    color: #94a3b8;
    max-width: 800px;
    margin: 0 auto;
}

/* --- 5. GRID CARD MINIMALISTE --- */
.cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 30px;
}
.card {
    position: relative;
    height: 320px;
    border-radius: 20px;
    overflow: hidden;
    border: 1px solid rgba(255,255,255,0.05);
    text-decoration: none !important;
    transition: all 0.4s ease;
}
.card-img {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    filter: brightness(0.4);
    transition: 0.5s ease;
}
.card-info {
    position: relative;
    z-index: 5;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 30px;
}
.card h3 { color: white !important; font-size: 1.5rem !important; margin: 0 !important; }
.card p { color: #94a3b8 !important; font-size: 0.9rem !important; margin-top: 8px !important; }

.card:hover { transform: translateY(-10px); border-color: #3b82f6 !important; }
.card:hover .card-img { filter: brightness(0.6) scale(1.05); }

.section-label {
    display: block;
    font-size: 0.8rem;
    font-weight: bold;
    color: #3b82f6;
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 10px;
}
</style>

<!-- HEADER SLIDER FULL WIDTH -->
<div class="hero-slider-container">
    <div class="hero-slide active" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
    <div class="hero-slide" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/proxmox-homelab.png');"></div>
    <div class="hero-slide" style="background-image: url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
    
   <div class="hero-overlay">
        <h1 class="hero-title">TUX<span>PI</span></h1>
        <div class="typing-wrap">
            <span id="typewriter"></span><span class="cursor">_</span>
        </div>
    </div>
</div>

<!-- CORPO DELLA PAGINA -->
<div class="content-section">
    
    <!-- MESSAGGIO DI BENVENUTO OTTIMIZZATO -->
  <div class="intro-box">
        <h2>🐧 Benvenuto su TuxPi</h2>
        <p>
            In questo blog si parla di tecnologia legata al mondo <strong>Linux</strong>, con un’attenzione particolare ai vantaggi che il sistema operativo del pinguino offre rispetto ad altri ambienti. 
            Troverai articoli di approfondimento, guide pratiche e soluzioni per scoprire un modo più libero, sicuro e personalizzabile di vivere la tecnologia.
        </p>
    </div>

    <!-- GRIGLIA SEZIONI -->
  <div id="sezioni" style="margin-bottom: 6rem;">
        <span class="section-label">Esplora l'ecosistema</span>
        <h2 style="font-size: 2.2rem !important; color: white; margin-bottom: 2rem;">Domina il tuo Hardware</h2>
        
<div class="cards-grid">
            <a href="/docs/proxmox" class="card">
                <div class="card-img" style="background-image: url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=800');"></div>
                <div class="card-info"><h3>Proxmox Lab</h3><p>Virtualizzazione estrema e nodi domestici.</p></div>
            </a>
            <a href="/docs/raspberry-pi" class="card">
                <div class="card-img" style="background-image: url('https://images.unsplash.com/photo-1629739945244-c7821487b257?q=80&w=800');"></div>
                <div class="card-info"><h3>Raspberry Pi</h3><p>IoT e server a basso consumo.</p></div>
            </a>
            <a href="/docs/self-hosting" class="card">
                <div class="card-img" style="background-image: url('https://images.unsplash.com/photo-1605745341112-85968b193ef5?q=80&w=800');"></div>
                <div class="card-info"><h3>Self-Hosting</h3><p>I tuoi dati, il tuo cloud privato.</p></div>
            </a>
            <a href="/docs/linux" class="card">
                <div class="card-img" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
                <div class="card-info"><h3>Cultura Linux</h3><p>Filosofia Open Source e terminale.</p></div>
            </a>
        </div>
  </div>

    <!-- ULTIMI ARTICOLI -->
  <div id="articoli">
        <span class="section-label">Aggiornamenti</span>
        <h2 style="font-size: 2.2rem !important; color: white; margin-bottom: 2rem;">Ultimi Articoli</h2>
        {{< latest-articles >}}
    </div>

</div>

<script>
// SCRIPT SCRITTURA E SLIDER
const texts = ["Linux & Open Source", "Proxmox Homelab", "Raspberry Pi & IoT"];
const slides = document.querySelectorAll('.hero-slide');
let wordIdx = 0, charIdx = 0, isDeleting = false;

function playEffect() {
    const current = texts[wordIdx];
    const el = document.getElementById('typewriter');
    
    el.textContent = isDeleting ? current.substring(0, charIdx--) : current.substring(0, charIdx++);
    
    let speed = isDeleting ? 50 : 120;
    if (!isDeleting && charIdx > current.length) { speed = 2500; isDeleting = true; }
    else if (isDeleting && charIdx === 0) {
        isDeleting = false;
        wordIdx = (wordIdx + 1) % texts.length;
        slides.forEach((s, i) => s.classList.toggle('active', i === wordIdx % slides.length));
        speed = 500;
    }
    setTimeout(playEffect, speed);
}
document.addEventListener('DOMContentLoaded', playEffect);
</script>
