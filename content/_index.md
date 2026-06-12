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
        <h1 class="intro-title">🐧 Benvenuto su TuxPi</h1>
        <p class="intro-text">
            In questo blog si parla di tecnologia legata al mondo <strong>Linux</strong>, con un’attenzione particolare ai vantaggi che il sistema operativo del pinguino offre rispetto ad altri ambienti.
            Troverai articoli di approfondimento, guide pratiche e recensioni su distribuzioni, software open source e soluzioni per ottimizzare l’esperienza d’uso.
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
// Slider Logic
const phrases = ["Linux & Open Source", "Proxmox Homelab", "Raspberry Pi & IoT"];
const slides = document.querySelectorAll('.hero-slide');
const textElement = document.getElementById('typing-text');
let currentIndex = 0, charIndex = 0, isDeleting = false, typeSpeed = 100;

function updateSlides(index) {
    slides.forEach((slide, i) => {
        slide.classList.toggle('active', i === index);
    });
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

document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if(target) target.scrollIntoView({ behavior: 'smooth' });
    });
});
</script>

<style>
/* --- AZZERAMENTO BARRE DI SCORRIMENTO --- */
html, body {
    scrollbar-width: none; /* Firefox */
    -ms-overflow-style: none; /* IE/Edge */
}
body::-webkit-scrollbar {
    display: none; /* Chrome, Safari, Opera */
}

/* --- RESET TEMA HEXTRA & FULL WIDTH --- */
:root { --hextra-max-content-width: 100% !important; }
.hx-mx-auto.hx-flex.hx-max-w-screen-xl { max-width: 100% !important; width: 100% !important; }
main.hx-w-full { max-width: 100% !important; }
aside, .hextra-breadcrumb, nav[aria-label="breadcrumb"], .hx-mt-2.hx-mb-6, h1.hx-text-4xl { display: none !important; }
hr, [class*="border-neutral"], .hx-border-t, .hx-border-b { border: none !important; display: none !important; }

/* --- LAYOUT PRINCIPALE --- */
.home-content-wrapper { 
    max-width: 1400px; 
    width: 92%; 
    margin: 0 auto; 
    padding-bottom: 5rem;
}

/* --- HERO SECTION --- */
.tuxpi-hero-container { 
    position: relative; width: 100vw; height: 90vh; 
    left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw; 
    margin-top: -3.5rem; overflow: hidden; background: #000; 
}
.hero-slide { 
    position: absolute; inset: 0; background-size: cover; background-position: center; 
    opacity: 0; transform: scale(1.1); transition: opacity 1.5s ease, transform 10s linear; 
}
.hero-slide.active { opacity: 1; transform: scale(1.02); z-index: 2; }
.hero-overlay { 
    position: relative; z-index: 10; height: 100%; 
    display: flex; align-items: center; justify-content: center; 
    background: radial-gradient(circle, transparent 20%, rgba(0,0,0,0.6) 90%); 
}
.hero-bottom-gradient { 
    position: absolute; bottom: 0; width: 100%; height: 250px; 
    background: linear-gradient(to top, #111 0%, transparent 100%); z-index: 11; 
}
.hero-title { 
    font-size: clamp(4rem, 18vw, 10rem) !important; font-weight: 900 !important; 
    color: white !important; margin: 0 !important; letter-spacing: -6px; 
}
.hero-title span { color: #3b82f6; text-shadow: 0 0 30px rgba(59, 130, 246, 0.5); }

.typing-container { margin-top: 1rem; font-family: 'JetBrains Mono', monospace; font-size: clamp(1rem, 4vw, 2rem); color: #cbd5e1; }
.cursor { animation: blink 0.8s infinite; color: #3b82f6; font-weight: bold; }
@keyframes blink { 50% { opacity: 0; } }

.hero-buttons { margin-top: 3rem; display: flex; gap: 15px; justify-content: center; }
.btn { 
    padding: 12px 30px; border-radius: 12px; font-weight: bold; 
    text-decoration: none !important; text-transform: uppercase; 
    transition: 0.3s ease; font-size: 0.85rem; letter-spacing: 1px; 
}
.btn-blue { background: #3b82f6; color: white !important; }
.btn-blue:hover { transform: translateY(-3px); box-shadow: 0 10px 20px rgba(59, 130, 246, 0.3); }
.btn-outline { border: 1px solid rgba(255,255,255,0.4); color: white !important; backdrop-filter: blur(5px); }
.btn-outline:hover { background: rgba(255,255,255,0.1); border-color: white; }

/* --- INTRO BOX --- */
.intro-box { text-align: center; padding: 6rem 0 4rem 0; max-width: 900px; margin: 0 auto; }
.intro-title { font-size: clamp(2rem, 5vw, 3.5rem) !important; font-weight: 800 !important; margin-bottom: 2rem !important; color: white; }
.intro-text { font-size: clamp(1.1rem, 2vw, 1.3rem); line-height: 1.8; color: #94a3b8; }

/* --- SEZIONI --- */
.section-container { padding: 4rem 0; }
.section-header { text-align: center; margin-bottom: 4rem; }
.section-tag { 
    background: rgba(59, 130, 246, 0.1); color: #3b82f6; padding: 6px 18px; 
    border-radius: 50px; font-size: 0.75rem; font-weight: 700; text-transform: uppercase; letter-spacing: 2px; 
}
.section-title { font-size: clamp(1.8rem, 4vw, 2.8rem) !important; font-weight: 800 !important; margin-top: 15px !important; color: white; }

/* --- GRID & CARD --- */
.tuxpi-cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 300px), 1fr));
    gap: 30px;
}
.tux-card {
    position: relative; height: 350px; border-radius: 24px; overflow: hidden;
    display: flex; align-items: flex-end; text-decoration: none !important;
    border: 1px solid rgba(255, 255, 255, 0.08) !important;
    transition: all 0.5s cubic-bezier(0.23, 1, 0.32, 1);
}
.card-bg { position: absolute; inset: 0; background-size: cover; background-position: center; filter: brightness(0.4); transition: 0.6s; z-index: 1; }
.card-content { 
    position: relative; z-index: 2; padding: 30px; width: 100%; 
    background: linear-gradient(to top, rgba(0,0,0,0.95), transparent); 
}
.card-icon { font-size: 2.5rem; margin-bottom: 15px; }
.tux-card h3 { color: #fff !important; font-size: 1.5rem !important; font-weight: 700 !important; margin-bottom: 8px !important; }
.tux-card p { color: #94a3b8 !important; font-size: 0.95rem !important; line-height: 1.5; }

.tux-card:hover { transform: translateY(-12px); border-color: #3b82f6 !important; box-shadow: 0 20px 40px rgba(0,0,0,0.4); }
.tux-card:hover .card-bg { filter: brightness(0.6) scale(1.1); }

/* --- RESPONSIVE ADJUSTMENTS --- */
@media (max-width: 768px) {
    .tuxpi-hero-container { height: 80vh; }
    .hero-buttons { flex-direction: column; align-items: center; }
    .btn { width: 80%; text-align: center; }
    .home-content-wrapper { width: 90%; }
}
</style>
