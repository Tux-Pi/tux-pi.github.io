---
title: "TuxPi"
toc: false
sidebar:
  hide: true
width: full
---

<style>
/* --- FIX SPAZIO A SINISTRA (RESET TEMA) --- */
/* Questo toglie i margini che Hextra mette a sinistra */
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
    padding: 0 !important;
}

/* --- BARRE DI SCORRIMENTO (APPAIONO AL PASSAGGIO) --- */
html {
    scrollbar-width: none; /* Firefox */
    -ms-overflow-style: none; /* IE */
    overflow-x: hidden;
}
html::-webkit-scrollbar { width: 10px; display: none; } /* Chrome/Safari */

html:hover { scrollbar-width: thin; }
html:hover::-webkit-scrollbar { display: block; }
::-webkit-scrollbar-thumb { background: #3b82f6; border-radius: 10px; }

/* --- PULIZIA ELEMENTI INUTILI --- */
aside, .hextra-toc, .hextra-breadcrumb, h1.hx-text-4xl, .hx-mb-6 { display: none !important; }

/* --- STILE PAGINA --- */
.hero-full {
    position: relative; width: 100%; height: 80vh; 
    background: #000; margin-top: -64px; overflow: hidden;
}
.slide { 
    position: absolute; inset: 0; background-size: cover; background-position: center; 
    opacity: 0; transition: opacity 1s; 
}
.slide.active { opacity: 1; }
.hero-text {
    position: relative; z-index: 10; height: 100%;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    background: rgba(0,0,0,0.4); text-align: center; color: white;
}
.hero-text h1 { font-size: clamp(3rem, 10vw, 8rem) !important; font-weight: 900 !important; margin: 0 !important; }
.hero-text h1 span { color: #3b82f6; }

.main-body { 
    max-width: 1500px; margin: 0 auto !important; padding: 4rem 2rem; 
}
.grid-cards {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px;
}
.card-item {
    position: relative; height: 300px; border-radius: 20px; overflow: hidden;
    border: 1px solid rgba(255,255,255,0.1); text-decoration: none !important; transition: 0.3s;
}
.card-img { position: absolute; inset: 0; background-size: cover; background-position: center; filter: brightness(0.4); transition: 0.4s; }
.card-info { position: relative; z-index: 2; height: 100%; display: flex; flex-direction: column; justify-content: flex-end; padding: 20px; color: white; }
.card-item:hover { transform: translateY(-10px); border-color: #3b82f6 !important; }
.card-item:hover .card-img { filter: brightness(0.6); }
</style>

<div class="hero-full">
    <div class="slide active" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
    <div class="slide" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/proxmox-homelab.png');"></div>
    <div class="hero-text">
        <h1>TUX<span>PI</span></h1>
        <div style="font-family: monospace; font-size: 1.5rem; margin-top: 10px;">
            <span id="type-txt"></span><span>_</span>
        </div>
    </div>
</div>

<div class="main-body">
    <div style="text-align: center; margin-bottom: 4rem;">
        <h2 style="font-size: 2.5rem !important; color: white;">🐧 Benvenuto su TuxPi</h2>
        <p style="color: #aaa; font-size: 1.2rem;">Esplora Linux, Proxmox e Raspberry Pi. Il tuo hub per l'Open Source.</p>
    </div>

  <div class="grid-cards">
        <a href="/docs/proxmox" class="card-item">
            <div class="card-img" style="background-image: url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=800');"></div>
            <div class="card-info"><h3>Proxmox</h3><p>Virtualizzazione.</p></div>
        </a>
        <a href="/docs/raspberry-pi" class="card-item">
            <div class="card-img" style="background-image: url('https://images.unsplash.com/photo-1629739945244-c7821487b257?q=80&w=800');"></div>
            <div class="card-info"><h3>Raspberry Pi</h3><p>IoT e Server.</p></div>
        </a>
        <a href="/docs/linux" class="card-item">
            <div class="card-img" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
            <div class="card-info"><h3>Linux</h3><p>Cultura Open Source.</p></div>
        </a>
    </div>

  <div style="margin-top: 5rem;">
        <h2 style="font-size: 2rem !important; color: white; border-bottom: 2px solid #3b82f6; display: inline-block; margin-bottom: 2rem;">Ultimi Articoli</h2>
       {{< latest-articles >}}
  </div>
</div>

<script>
const words = ["Linux & Open Source", "Proxmox Homelab", "Raspberry Pi & IoT"];
let i = 0, j = 0, del = false;
function type() {
    const cur = words[i], el = document.getElementById('type-txt');
    el.textContent = cur.substring(0, j);
    if (!del && j < cur.length) { j++; setTimeout(type, 150); }
    else if (del && j > 0) { j--; setTimeout(type, 50); }
    else {
        del = !del;
        if (!del) i = (i + 1) % words.length;
        setTimeout(type, del ? 2000 : 500);
        if(!del) {
            const slides = document.querySelectorAll('.slide');
            slides.forEach((s, idx) => s.classList.toggle('active', idx === i % slides.length));
        }
    }
}
document.addEventListener('DOMContentLoaded', type);
</script>
