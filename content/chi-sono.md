---
title: "Chi Sono"
toc: false
# width: full in Hextra spesso non basta, lo forziamo noi sotto
---
<style>
/* --- 1. NASCONDE IL TITOLO DELLA PAGINA --- */
/* Questo elimina la scritta "Chi Sono" generata dal tema e i relativi spazi */
h1.hx-text-4xl, 
.hx-mt-2.hx-mb-6, 
nav[aria-label="breadcrumb"], 
.hextra-breadcrumb { 
    display: none !important; 
}

/* --- 2. FORZA LA LARGHEZZA TOTALE (Elimina spazio a sinistra e destra) --- */
/* Rimuoviamo i limiti del contenitore centrale di Hextra */
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

/* --- 3. FASCIA BLU FULL WIDTH --- */
.about-hero-full {
    width: 100%;
    min-height: 400px;
    /* Immagine di sfondo con overlay scuro */
    background: linear-gradient(rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.9)), 
                url('https://images.unsplash.com/photo-1510511459019-5dee997dd1db?q=80&w=2000');
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    border-bottom: 2px solid #3b82f6;
    margin-top: -64px; /* Saliamo sotto la navbar */
    padding: 100px 20px;
}

.about-hero-full h1 {
    font-size: clamp(2.5rem, 8vw, 4.5rem) !important;
    font-weight: 900 !important;
    color: white !important;
    margin: 0 !important;
    letter-spacing: -2px;
}

.blue-glow {
    color: #3b82f6;
    text-shadow: 0 0 20px rgba(59, 130, 246, 0.4);
}

/* --- 4. CONTENUTO TESTUALE (Centrato ma largo) --- */
.about-body {
    max-width: 1200px; /* Qui decidi quanto vuoi largo il contenuto sotto la fascia */
    margin: 0 auto !important;
    padding: 5rem 2rem;
    color: #cbd5e1;
    line-height: 1.8;
}

.about-body h2 {
    font-size: 2.5rem !important;
    color: white !important;
    margin: 3rem 0 1.5rem 0 !important;
    font-weight: 800 !important;
}

/* Griglia Homelab */
.homelab-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    margin: 30px 0;
}

.homelab-box {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.1);
    padding: 25px;
    border-radius: 15px;
    transition: 0.3s;
}

.homelab-box:hover {
    border-color: #3b82f6;
    background: rgba(59, 130, 246, 0.05);
}

.homelab-box strong { color: #3b82f6; display: block; margin-bottom: 10px; font-size: 1.2rem; }

.btn-contatti {
    display: inline-block;
    background: #3b82f6;
    color: white !important;
    padding: 12px 30px;
    border-radius: 8px;
    text-decoration: none !important;
    font-weight: bold;
    margin-top: 2rem;
}
</style>

<!-- FASCIA BLU ESTESA A TUTTO L'ORIZZONTE -->
<div class="about-hero-full">
    <div>
        <span style="color:#3b82f6; font-weight:bold; text-transform:uppercase; letter-spacing:3px;">L'anima del progetto</span>
        <h1>Dietro le quinte di <span class="blue-glow">TuxPi</span></h1>
        <p style="color:#94a3b8; font-size:1.3rem; max-width:700px; margin: 15px auto;">Passione per l'Open Source, curiosità per l'hardware e libertà digitale.</p>
    </div>
</div>

<!-- CONTENUTO PAGINA -->
<div class="about-body">

  <h2>🐧 Chi è TuxMaker?</h2>
    <p>
        Ciao! Sono <strong>TuxMaker</strong>, l'ideatore di questo spazio. 
        Il progetto <span class="blue-glow">TuxPi</span> è nato originariamente su <code>tuxpi.ddns.net</code> come un piccolo esperimento domestico su un LXC di Proxmox. 
        Oggi è un blog dedicato alla cultura Linux e al self-hosting, ospitato con orgoglio su GitHub per condividere questa passione con la community.
    </p>

  <hr style="opacity:0.1; margin: 4rem 0;">

  <h2>🛠️ Il mio Homelab</h2>
    <p>Recensisco distro Linux e illustro soluzioni Docker/Proxmox testate direttamente nel mio garage digitale:</p>
    
  <div class="homelab-grid">
        <div class="homelab-box">
            <strong>Server Principale</strong>
            <p>Nodo Proxmox VE su hardware x86 per virtualizzazione pesante.</p>
        </div>
        <div class="homelab-box">
            <strong>Storage</strong>
            <p>Server Samba su Proxmox per la gestione centralizzata dei file.</p>
        </div>
        <div class="homelab-box">
            <strong>Container</strong>
            <p>Oltre 10 servizi Docker gestiti tramite Portainer e Docker Compose.</p>
        </div>
    </div>

  <hr style="opacity:0.1; margin: 4rem 0;">

  <h2>🚀 La Missione</h2>
    <p>Attraverso questo blog voglio far capire che esiste un modo più libero, sicuro e personalizzabile di vivere la tecnologia:</p>
    
  <div style="background: rgba(255,255,255,0.02); padding: 30px; border-radius: 20px;">
        <ul style="list-style: none; padding: 0; margin: 0;">
            <li style="margin-bottom: 15px;">🔹 <strong>Cultura Linux</strong>: Dimostrare che l'Open Source è la scelta migliore per tutti.</li>
            <li style="margin-bottom: 15px;">🔹 <strong>Supporto Pratico</strong>: Condividere script e configurazioni testate sul campo.</li>
            <li style="margin-bottom: 15px;">🔹 <strong>Riciclo Tecnologico</strong>: Dare nuova vita a vecchio hardware con sistemi leggeri e potenti.</li>
        </ul>
    </div>

  <div style="text-align: center;">
        <a href="/docs" class="btn-contatti">Esplora le Guide</a>
    </div>

</div>
