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

/* Lightbox */
#lightbox {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.9);
  align-items: center;
  justify-content: center;
  z-index: 999;
}
#lightbox img {
  max-width: 85%;
  max-height: 85%;
  border-radius: 4px;
}

#lightbox-close {
  position: absolute;
  top: 20px;
  right: 30px;
  color: #fff;
  font-size: 2.2rem;
  line-height: 1;
  cursor: pointer;
  user-select: none;
  background: none;
  border: none;
}
#lightbox-close:hover {
  color: #ccc;
}

.lightbox-nav {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  color: #fff;
  font-size: 2.5rem;
  cursor: pointer;
  user-select: none;
  background: rgba(0,0,0,0.3);
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
}
.lightbox-nav:hover {
  background: rgba(0,0,0,0.6);
}
#lightbox-prev { left: 20px; }
#lightbox-next { right: 20px; }

@media (max-width: 600px) {
  .lightbox-nav { font-size: 1.8rem; padding: 0.4rem 0.7rem; }
  #lightbox-close { font-size: 1.8rem; top: 12px; right: 16px; }
}
</style>

<div class="gallery-grid" id="gallery-grid"></div>

<div id="lightbox">
  <button id="lightbox-close" aria-label="Bezárás">&times;</button>
  <button class="lightbox-nav" id="lightbox-prev" aria-label="Előző">&#8249;</button>
  <img id="lightbox-img" src="" alt="">
  <button class="lightbox-nav" id="lightbox-next" aria-label="Következő">&#8250;</button>
</div>

<script>
// Ide írd a képek fájlneveit az assets/gallery mappában
const images = [
  "kep1.jpg",
  "kep2.jpg",
  "kep3.jpg"
];

const basePath = "/assets/gallery/";
let currentIndex = 0;

const grid = document.getElementById('gallery-grid');
images.forEach((file, i) => {
  const img = document.createElement('img');
  img.src = basePath + file;
  img.alt = "Kép " + (i + 1);
  img.addEventListener('click', () => openLightbox(i));
  grid.appendChild(img);
});

const lightbox = document.getElementById('lightbox');
const lightboxImg = document.getElementById('lightbox-img');

function openLightbox(index) {
  currentIndex = index;
  updateLightboxImage();
  lightbox.style.display = 'flex';
}

function closeLightbox() {
  lightbox.style.display = 'none';
}

function updateLightboxImage() {
  lightboxImg.src = basePath + images[currentIndex];
}

function showNext() {
  currentIndex = (currentIndex + 1) % images.length;
  updateLightboxImage();
}

function showPrev() {
  currentIndex = (currentIndex - 1 + images.length) % images.length;
  updateLightboxImage();
}

document.getElementById('lightbox-close').addEventListener('click', closeLightbox);
document.getElementById('lightbox-next').addEventListener('click', showNext);
document.getElementById('lightbox-prev').addEventListener('click', showPrev);

// Kattintás a sötét háttérre is zárjon be, de a kép/gombok kattintása ne
lightbox.addEventListener('click', (e) => {
  if (e.target === lightbox) closeLightbox();
});

// Billentyűzet: Escape zár, nyilak lapoznak
document.addEventListener('keydown', (e) => {
  if (lightbox.style.display !== 'flex') return;
  if (e.key === 'Escape') closeLightbox();
  if (e.key === 'ArrowRight') showNext();
  if (e.key === 'ArrowLeft') showPrev();
});
</script>
