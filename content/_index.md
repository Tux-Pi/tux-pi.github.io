---
title: "TuxPi - Home Page"
---

<!-- SEZIONE HERO FULL WIDTH (Ignora i margini del tema) -->
<div class="hero-breakout">
  <div class="hero-inner">
    
    <!-- Immagine di Sfondo con Effetto Parallasse -->
    <div class="hero-bg"></div>
    
    <!-- Overlay Scuro per Leggibilità -->
    <div class="hero-overlay"></div>

    <!-- Contenuto Centrale -->
    <div class="hero-content">
      <div class="hero-badge">Progetto Linux & Open Source</div>
      <h1 class="hero-title">TUXPI</h1>
      
      <div class="hero-subtitle-container">
        <span class="hero-prefix">> </span>
        <span class="hero-typing"></span>
        <span class="hero-cursor">_</span>
      </div>

      <div class="hero-buttons">
        <a href="/blog/" class="btn-primary">Esplora Articoli</a>
        <a href="/docs/proxmox/" class="btn-secondary">Guida Proxmox</a>
      </div>
    </div>

  </div>
</div>

<style>
/* TRUCCO PER ROMPERE I MARGINI DEL TEMA */
.hero-breakout {
    position: relative;
    width: 100vw;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
    margin-top: -2rem; /* Allinea all'inizio del contenuto */
    margin-bottom: 4rem;
}

.hero-inner {
    position: relative;
    height: 85vh; /* Prende l'85% dell'altezza dello schermo */
    min-height: 500px;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
}

.hero-bg {
    position: absolute;
    inset: 0;
    background-image: url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070');
    background-size: cover;
    background-position: center;
    transform: scale(1.1); /* Per un leggero effetto profondità */
}

.hero-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to bottom, rgba(0,0,0,0.7), rgba(0,0,0,0.4), rgba(0,0,0,0.8));
}

.hero-content {
    position: relative;
    z-index: 10;
    text-align: center;
    color: white;
    padding: 0 20px;
    width: 100%;
}

.hero-badge {
    background: #2563eb;
    color: white;
    display: inline-block;
    padding: 6px 15px;
    border-radius: 50px;
    font-weight: 700;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 1rem;
}

.hero-title {
    font-size: clamp(4rem, 15vw, 10rem) !important; /* Testo GIGANTE */
    font-weight: 900 !important;
    line-height: 0.8;
    margin: 0 !important;
    letter-spacing: -5px;
    color: white;
    text-shadow: 0 10px 30px rgba(0,0,0,0.5);
}

.hero-subtitle-container {
    margin-top: 1.5rem;
    font-family: 'Courier New', Courier, monospace;
    font-size: clamp(1.2rem, 4vw, 2.5rem);
    font-weight: 400;
    color: #cbd5e1;
}

.hero-typing::after {
    content: "";
    animation: typing-text 12s infinite;
}

@keyframes typing-text {
    0%, 25% { content: "Il server del Pinguino"; }
    26%, 50% { content: "Mondo Raspberry Pi"; }
    51%, 75% { content: "Homelab con Proxmox"; }
    76%, 100% { content: "Libertà Digitale"; }
}

.hero-cursor {
    animation: blink 0.8s infinite;
    color: #2563eb;
}

@keyframes blink { 50% { opacity: 0; } }

.hero-buttons {
    margin-top: 3rem;
    display: flex;
    justify-content: center;
    gap: 20px;
}

.btn-primary {
    background: white;
    color: black;
    padding: 15px 35px;
    border-radius: 50px;
    font-weight: 700;
    text-decoration: none;
    transition: 0.3s;
}
.btn-primary:hover { background: #2563eb; color: white; transform: scale(1.05); }

.btn-secondary {
    border: 2px solid rgba(255,255,255,0.4);
    color: white;
    padding: 15px 35px;
    border-radius: 50px;
    font-weight: 700;
    text-decoration: none;
    transition: 0.3s;
}
.btn-secondary:hover { border-color: white; background: rgba(255,255,255,0.1); }
</style>

---

## 🛠️ Le sezioni principali di TuxPi
Bentornato su **TuxPi**. Qui trovi tutto ciò che serve per gestire il tuo hardware e i tuoi server Linux.

{{< cards >}}
  {{< card link="/blog/" title="Blog & News" icon="book-open" subtitle="Approfondimenti settimanali." >}}
  {{< card link="/docs/proxmox/" title="Proxmox Lab" icon="cog" subtitle="Virtualizzazione estrema." >}}
  {{< card link="/docs/raspberry-pi/" title="Raspberry Pi" icon="terminal" subtitle="Progetti hardware." >}}
{{< /cards >}}
