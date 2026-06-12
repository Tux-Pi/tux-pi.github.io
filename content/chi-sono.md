---
title: Chi Sono
  hide: true
toc: false
sidebar:
  hide: true
width: full
---
<style>
/* --- FIX STRUTTURALE PER PAGINA PULITA --- */
/* Rimuove i blocchi del tema Hextra che stringono la pagina */
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

/* Nasconde titoli automatici, breadcrumbs e sidebar del tema */
aside, .hextra-toc, .hextra-breadcrumb, h1.hx-text-4xl, .hx-mb-6, nav[aria-label="breadcrumb"] { 
    display: none !important; 
}

/* --- HERO CHI SIAMO (FULL WIDTH) --- */
.about-hero {
    width: 100%;
    min-height: 50vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(rgba(15, 23, 42, 0.85), rgba(15, 23, 42, 0.85)), 
                url('https://images.unsplash.com/photo-1510511459019-5dee997dd1db?q=80&w=2000');
    background-size: cover;
    background-position: center;
    text-align: center;
    padding: 4rem 1rem;
    margin-top: -64px; /* Compensa la navbar */
}

.about-hero-content {
    max-width: 800px;
    margin: 0 auto;
}

.about-hero-content h1 {
    font-size: clamp(2.5rem, 8vw, 4.5rem) !important;
    font-weight: 900 !important;
    color: white !important;
    margin: 1.5rem 0 !important;
    letter-spacing: -2px;
}

.badge-about {
    background: rgba(59, 130, 246, 0.2);
    color: #3b82f6;
    padding: 6px 20px;
    border-radius: 50px;
    font-size: 0.85rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 2px;
}

/* --- WRAPPER CONTENUTO (CENTRATO E PULITO) --- */
.about-wrapper {
    max-width: 850px; /* Testo stretto per leggibilità ottimale */
    margin: 0 auto !important;
    padding: 5rem 1.5rem;
    color: #cbd5e1;
    line-height: 1.8;
}

.about-wrapper h2 {
    font-size: 2.2rem !important;
    color: white !important;
    margin-top: 3rem !important;
    margin-bottom: 1.5rem !important;
    font-weight: 800 !important;
}

.blue-text { color: #3b82f6; font-weight: bold; }

/* --- TECH GRID REFINEMENT --- */
.tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
    margin: 2.5rem 0;
}

.tech-item {
    background: rgba(255, 255, 255, 0.03);
    padding: 2rem;
    border-radius: 20px;
    border: 1px solid rgba(255, 255, 255, 0.05);
    transition: all 0.3s ease;
}

.tech-item:hover {
    transform: translateY(-5px);
    border-color: #3b82f6;
    background: rgba(59, 130, 246, 0.05);
}

.tech-item strong {
    display: block;
    color: #3b82f6;
    font-size: 1.1rem;
    margin-bottom: 0.5rem;
}

.tech-item p {
    font-size: 0.95rem;
    margin: 0;
    color: #94a3b8;
}

/* --- LISTA MISSIONE --- */
.mission-list {
    list-style: none;
    padding: 0;
}

.mission-list li {
    margin-bottom: 1.5rem;
    padding-left: 2rem;
    position: relative;
}

.mission-list li::before {
    content: "→";
    position: absolute;
    left: 0;
    color: #3b82f6;
    font-weight: bold;
}

hr {
    border: 0;
    height: 1px;
    background: linear-gradient(to right, transparent, rgba(59, 130, 246, 0.5), transparent);
    margin: 4rem 0;
}
</style>

<div class="about-hero">
    <div class="about-hero-content">
        <span class="badge-about">L'anima del progetto</span>
        <h1>Dietro le quinte di <span class="blue-text">TuxPi</span></h1>
        <p style="font-size: 1.2rem; color: #94a3b8;">Passione per l'Open Source, curiosità per l'hardware e una missione: la libertà digitale.</p>
    </div>
</div>

<div class="about-wrapper">

<h2>🐧 Chi è TuxMaker?</h2>
    <p>
        Ciao! Sono <strong>TuxMaker</strong>, l'ideatore e curatore di questo spazio. 
        Il progetto <span class="blue-text">TuxPi</span> è nato originariamente su <code>tuxpi.ddns.net</code> come un piccolo esperimento domestico su un LXC di Proxmox. 
        Con il tempo, il blog si è evoluto e, per raggiungere più appassionati, ho deciso di trasferirlo su GitHub.
    </p>

<hr>

<h2>🛠️ Il mio Homelab</h2>
<p>Recensisco distro Linux e illustro soluzioni con Docker e Proxmox, testando tutto nel mio "garage" digitale:</p>

<div class="tech-grid">
        <div class="tech-item">
            <strong>Server Principale</strong>
            <p>Nodo Proxmox VE su hardware x86 per virtualizzazione pesante.</p>
        </div>
        <div class="tech-item">
            <strong>Storage</strong>
            <p>Server Samba ottimizzato per l'archiviazione dati locale.</p>
        </div>
        <div class="tech-item">
            <strong>Containerizzazione</strong>
            <p>Oltre 10 servizi Docker gestiti agilmente tramite Portainer.</p>
        </div>
    </div>

<hr>

<h2>🚀 La Missione di TuxPi</h2>
    <p>Questo sito non è solo un manuale tecnico, ma un hub per condividere la filosofia del "fai-da-te" digitale:</p>

<ul class="mission-list">
        <li><strong>Divulgare la cultura Linux</strong>: Dimostrare che esiste un'alternativa libera e sicura ai sistemi proprietari.</li>
        <li><strong>Supportare la Community</strong>: Condividere configurazioni e script pronti all'uso per risparmiare tempo prezioso.</li>
        <li><strong>Promuovere il Riciclo Tech</strong>: Valorizzare vecchio hardware rendendolo più potente di costosi servizi cloud.</li>
    </ul>

<div style="margin-top: 4rem; padding: 2rem; background: rgba(59, 130, 246, 0.1); border-radius: 20px; text-align: center;">
        <p style="margin: 0;">Vuoi scambiare due chiacchiere? <a href="/contatti" class="blue-text">Contattami qui</a> e costruiamo qualcosa insieme!</p>
    </div>

</div>
