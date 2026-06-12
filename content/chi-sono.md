---
title: "Chi Sono"
toc: false
sidebar:
  hide: true
width: full
---
<style>
/* --- 1. RESET TOTALE PER LARGHEZZA FULL --- */
/* Forza il contenitore di Hextra ad allargarsi al 100% */
.hx-mx-auto.hx-flex.hx-max-w-screen-xl {
    max-width: 100% !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
    display: block !important;
}

/* Nasconde il titolo della pagina generato automaticamente e i breadcrumb */
h1.hx-text-4xl, 
.hx-mt-2.hx-mb-6, 
nav[aria-label="breadcrumb"],
.hextra-breadcrumb { 
    display: none !important; 
}

main.hx-w-full {
    max-width: 100% !important;
    width: 100% !important;
}

/* --- 2. HERO CHI SIAMO (FASCIA BLU FULL WIDTH) --- */
.about-hero {
    width: 100%; /* Ora va da bordo a bordo */
    background: linear-gradient(rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.9)), 
                url('https://images.unsplash.com/photo-1510511459019-5dee997dd1db?q=80&w=2000');
    background-size: cover;
    background-position: center;
    padding: 6rem 1rem;
    text-align: center;
    border-bottom: 1px solid rgba(59, 130, 246, 0.3);
    margin-top: -64px; /* Incastra sotto la navbar */
}

.about-hero-content {
    max-width: 1000px;
    margin: 0 auto;
}

.about-hero-content h1 {
    font-size: clamp(2.5rem, 7vw, 4rem) !important;
    font-weight: 900 !important;
    color: white !important;
    margin: 1rem 0 !important;
    letter-spacing: -2px;
}

.blue-text { color: #3b82f6; }

.badge-about {
    background: rgba(59, 130, 246, 0.2);
    color: #3b82f6;
    padding: 6px 18px;
    border-radius: 50px;
    font-size: 0.8rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 2px;
}

/* --- 3. WRAPPER TESTO (CENTRATO E LEGGIBILE) --- */
.about-wrapper {
    max-width: 900px; /* Il testo non deve essere largo quanto lo schermo per essere leggibile */
    margin: 0 auto !important;
    padding: 5rem 2rem;
    line-height: 1.8;
    color: #cbd5e1;
}

.about-wrapper h2 {
    font-size: 2.2rem !important;
    color: white !important;
    margin: 3rem 0 1.5rem 0 !important;
    font-weight: 800 !important;
}

/* Griglia Tech */
.tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
    margin: 2rem 0;
}

.tech-item {
    background: rgba(255, 255, 255, 0.03);
    padding: 1.5rem;
    border-radius: 15px;
    border-left: 4px solid #3b82f6;
    transition: 0.3s;
}

.tech-item:hover {
    background: rgba(59, 130, 246, 0.05);
    transform: translateX(5px);
}

.tech-item strong { display: block; color: #3b82f6; margin-bottom: 5px; }
.tech-item p { font-size: 0.9rem; margin: 0; color: #94a3b8; }

hr { border: 0; height: 1px; background: rgba(255,255,255,0.1); margin: 4rem 0; }
</style>

<!-- PARTE GRAFICA FULL WIDTH -->
<div class="about-hero">
    <div class="about-hero-content">
        <span class="badge-about">L'anima del progetto</span>
        <h1>Dietro le quinte di <span class="blue-text">TuxPi</span></h1>
        <p style="color: #94a3b8; font-size: 1.2rem;">Passione per l'Open Source, curiosità per l'hardware e libertà digitale.</p>
    </div>
</div>

<!-- PARTE TESTUALE CENTRATA -->
<div class="about-wrapper">

  <h2>🐧 Chi è TuxMaker?</h2>
    <p>
        Ciao! Sono <strong>TuxMaker</strong>, l'ideatore di questo spazio. 
        Il progetto <span class="blue-text">TuxPi</span> è nato come un esperimento domestico su un LXC di Proxmox. 
        Oggi è un blog dedicato alla cultura Linux e al self-hosting, ospitato con orgoglio su GitHub.
    </p>

  <hr>

  <h2>🛠️ Il mio Homelab</h2>
    <div class="tech-grid">
        <div class="tech-item">
            <strong>Server Principale</strong>
            <p>Proxmox VE su hardware x86 per virtualizzazione pesante.</p>
        </div>
        <div class="tech-item">
            <strong>Storage</strong>
            <p>NAS Samba centralizzato per backup e dati.</p>
        </div>
        <div class="tech-item">
            <strong>Docker</strong>
            <p>Oltre 10 servizi gestiti con Portainer e Docker Compose.</p>
        </div>
    </div>

  <hr>

  <h2>🚀 La Missione</h2>
    <p>Voglio dimostrare che la tecnologia può essere libera, sicura e divertente attraverso:</p>
    <ul style="list-style: none; padding: 0;">
        <li style="margin-bottom: 1rem;">🔹 <strong>Divulgazione</strong>: Linux come alternativa reale ai sistemi chiusi.</li>
        <li style="margin-bottom: 1rem;">🔹 <strong>Supporto</strong>: Script e guide per facilitare la vita ai sysadmin casalinghi.</li>
        <li style="margin-bottom: 1rem;">🔹 <strong>Riciclo</strong>: Dare nuova vita a vecchio hardware con il software libero.</li>
    </ul>

</div>
