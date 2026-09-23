---
layout: page
title: Galéria
permalink: /galeria/
---

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 12px;
  margin-top: 1.5rem;
}
.gallery-grid img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 6px;
  cursor: pointer;
  transition: transform 0.15s ease;
}
.gallery-grid img:hover {
  transform: scale(1.03);
}

/* Egyszerű lightbox */
#lightbox {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.85);
  align-items: center;
  justify-content: center;
  z-index: 999;
  cursor: zoom-out;
}
#lightbox img {
  max-width: 90%;
  max-height: 90%;
  border-radius: 4px;
}
</style>

<div class="gallery-grid">
  <img src="/assets/gallery/kep1.jpg" alt="Kép 1" onclick="openLightbox(this.src)">
  <img src="/assets/gallery/kep2.jpg" alt="Kép 2" onclick="openLightbox(this.src)">
  <img src="/assets/gallery/kep3.jpg" alt="Kép 3" onclick="openLightbox(this.src)">
</div>

<div id="lightbox" onclick="closeLightbox()">
  <img id="lightbox-img" src="" alt="">
</div>

<script>
function openLightbox(src) {
  document.getElementById('lightbox-img').src = src;
  document.getElementById('lightbox').style.display = 'flex';
}
function closeLightbox() {
  document.getElementById('lightbox').style.display = 'none';
}
</script>
