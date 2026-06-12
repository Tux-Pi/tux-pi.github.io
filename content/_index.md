---
title: "TuxPi"
#toc: false
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
            In questo blog si parla di tecnologia legata al mondo <strong>Linux</strong>, con un’attenzione particolare ai vantaggi dell’open source. Guide pratiche, Proxmox, Raspberry e tutto ciò che serve per dominare il tuo hardware.
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
                <div class="card-content"><h3>Proxmox Lab</h3><p>Virtualizzazione estrema e nodi domestici.</p></div>
            </a>
            <a href="/docs/raspberry-pi" class="tux-card">
                <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1629739945244-c7821487b257?q=80&w=800');"></div>
                <div class="card-content"><h3>Mondo Raspberry</h3><p>IoT e server a basso consumo.</p></div>
            </a>
            <a href="/docs/self-hosting" class="tux-card">
                <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1605745341112-85968b193ef5?q=80&w=800');"></div>
                <div class="card-content"><h3>Self-Hosting</h3><p>Docker e servizi cloud privati.</p></div>
            </a>
            <a href="/docs/linux" class="tux-card">
                <div class="card-bg" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
                <div class="card-content"><h3>Cultura Linux</h3><p>Guide al terminale e filosofia Open Source.</p></div>
            </a>
        </div>
    </div>

    <div id="articoli" class="section-container">
        <div class="section-header">
            <span class="section-tag">News</span>
            <h2 class="section-title">Ultimi Articoli</h2>
        </div>
        {{< latest-articles >}}
    </div>
</div>

<script>
const phrases = ["Linux & Open Source", "Proxmox Homelab", "Raspberry Pi & IoT"];
const slides = document.querySelectorAll('.hero-slide');
const textElement = document.getElementById('typing-text');
let currentIndex = 0, charIndex = 0, isDeleting = false, typeSpeed = 100;
function updateSlides(index) { slides.forEach((slide, i) => { slide.classList.toggle('active', i === index); }); }
function typeEffect() {
    const currentPhrase = phrases[currentIndex];
    if (isDeleting) { textElement.textContent = currentPhrase.substring(0, charIndex - 1); charIndex--; typeSpeed = 40; 
    } else { textElement.textContent = currentPhrase.substring(0, charIndex + 1); charIndex++; typeSpeed = 120; }
    if (!isDeleting && charIndex === currentPhrase.length) { isDeleting = true; typeSpeed = 2000; 
    } else if (isDeleting && charIndex === 0) { isDeleting = false; currentIndex = (currentIndex + 1) % phrases.length; updateSlides(currentIndex); typeSpeed = 500; }
    setTimeout(typeEffect, typeSpeed);
}
document.addEventListener('DOMContentLoaded', typeEffect);
</script>

<style>
/* --- 1. BARRE DI SCORRIMENTO INTELLIGENTI --- */
/* Nasconde la barra di default */
html {
    scrollbar-width: none; /* Firefox */
    -ms-overflow-style: none; /* IE */
}
html::-webkit-scrollbar { width: 8px; display: none; } /* Chrome/Safari */

/* Mostra la barra quando il mouse si muove sulla pagina */
html:hover { scrollbar-width: thin; }
html:hover::-webkit-scrollbar { display: block; }
::-webkit-scrollbar-track { background: rgba(0,0,0,0.1); }
::-webkit-scrollbar-thumb { background: #3b82f6; border-radius: 10px; }

/* --- 2. ELIMINAZIONE SPAZIO SINISTRO E LARGO --- */
/* Forza il reset dei margini di Hextra */
.hx-mx-auto.hx-flex.hx-max-w-screen-xl {
    max-width: 100% !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
    display: block !important; /* Rimuove il comportamento flex che spinge a destra */
}

/* Allarga il contenitore principale */
main.hx-w-full {
    max-width: 100% !important;
    width: 100% !important;
    padding: 0 !important;
}

/* Rimuove i padding interni della pagina */
.hx-w-full.hx-break-words {
    max-width: 100% !important;
    padding-left: 0 !important;
    padding-right: 0 !important;
}

/* Nasconde elementi inutili che creano spazi bianchi */
aside, .hextra-toc, .hextra-breadcrumb, h1.hx-text-4xl { display: none !important; }

/* --- 3. HERO (A TUTTA LARGHEZZA) --- */
.tuxpi-hero-container { 
    position: relative; width: 100%; height: 80vh; 
    overflow: hidden; background: #000; margin-top: -64px; /* Compensa navbar */
}
.hero-slide { position: absolute; inset: 0; background-size: cover; background-position: center; opacity: 0; transition: opacity 1.2s ease; }
.hero-slide.active { opacity: 1; z-index: 1; }
.hero-overlay { position: relative; z-index: 10; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; background: rgba(0,0,0,0.5); }

.hero-title { font-size: clamp(3rem, 12vw, 8rem) !important; font-weight: 900 !important; color: white !important; margin: 0 !important; letter-spacing: -4px; }
.hero-title span { color: #3b82f6; }

/* --- 4. CONTENUTO (LARGO MA CENTRATO) --- */
.home-content-wrapper { 
    max-width: 1600px; /* Molto largo */
    width: 95%; 
    margin: 0 auto !important; /* Centra il blocco del contenuto nel nuovo spazio totale */
    padding: 4rem 0;
}

.tuxpi-cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    margin-top: 3rem;
}

.tux-card {
    position: relative; height: 350px; border-radius: 24px; overflow: hidden;
    display: flex; align-items: flex-end; text-decoration: none !important;
    border: 1px solid rgba(255,255,255,0.1) !important; transition: 0.4s;
}
.card-bg { position: absolute; inset: 0; background-size: cover; background-position: center; filter: brightness(0.4); transition: 0.5s; }
.card-content { position: relative; z-index: 2; padding: 30px; width: 100%; background: linear-gradient(to top, #000, transparent); }
.tux-card h3 { color: white !important; font-size: 1.5rem !important; margin: 0 !important; }
.tux-card p { color: #94a3b8 !important; margin: 5px 0 0 0 !important; font-size: 0.95rem; }

.tux-card:hover { transform: translateY(-10px); border-color: #3b82f6 !important; }
.tux-card:hover .card-bg { filter: brightness(0.6) scale(1.05); }

.intro-box { text-align: center; padding: 4rem 0; }
.section-header { text-align: center; margin-bottom: 2rem; }
.section-tag { color: #3b82f6; font-weight: bold; text-transform: uppercase; letter-spacing: 2px; font-size: 0.8rem; }
.section-title { font-size: 2.5rem !important; font-weight: 800 !important; color: white; }

.btn { padding: 12px 25px; border-radius: 10px; font-weight: bold; text-decoration: none !important; margin: 0 10px; transition: 0.3s; }
.btn-blue { background: #3b82f6; color: white !important; }
.btn-outline { border: 1px solid white; color: white !important; }

@media (max-width: 768px) {
    .hero-title { font-size: 4rem !important; }
    .home-content-wrapper { width: 92%; }
}
</style>
