---
layout: page
title: Galéria
permalink: /galeria/
---

<style>
.gallery-section {
  margin-bottom: 3rem;
}
.gallery-section h2 {
  margin-bottom: 0.5rem;
}
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 12px;
  margin-top: 1rem;
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

<div id="galleries-container"></div>

<div id="lightbox">
  <button id="lightbox-close" aria-label="Bezárás">&times;</button>
  <button class="lightbox-nav" id="lightbox-prev" aria-label="Előző">&#8249;</button>
  <img id="lightbox-img" src="" alt="">
  <button class="lightbox-nav" id="lightbox-next" aria-label="Következő">&#8250;</button>
</div>

<script>
// Minden galériához: cím, mappa neve, és a fájlnevek (ugyanaz a fájlnév kell
// mindkét mappában – csak a mappa különbözteti meg a kicsi és nagy verziót).
const galleries = [
  {
    title: "Bútorok",
    folder: "butorok",
    images: ["kep1.jpg", "kep2.jpg", "kep3.jpg"]
  },
  {
    title: "Fa díszek",
    folder: "diszek",
    images: ["kep1.jpg", "kep2.jpg"]
  }
];

// A kicsinyített képek ide kerülnek: assets/gallery/thumbs/<folder>/<fájlnév>
// Az eredeti (nagy) képek ide kerülnek:      assets/gallery/full/<folder>/<fájlnév>
const thumbsPath = "/assets/gallery/thumbs/";
const fullPath = "/assets/gallery/full/";

let currentGallery = 0;
let currentIndex = 0;

const container = document.getElementById('galleries-container');

galleries.forEach((gallery, gIndex) => {
  const section = document.createElement('div');
  section.className = 'gallery-section';

  const heading = document.createElement('h2');
  heading.textContent = gallery.title;
  section.appendChild(heading);

  const grid = document.createElement('div');
  grid.className = 'gallery-grid';

  gallery.images.forEach((file, iIndex) => {
    const img = document.createElement('img');
    img.src = thumbsPath + gallery.folder + "/" + file;
    img.alt = gallery.title + " – kép " + (iIndex + 1);
    img.loading = "lazy";
    img.addEventListener('click', () => openLightbox(gIndex, iIndex));
    grid.appendChild(img);
  });

  section.appendChild(grid);
  container.appendChild(section);
});

const lightbox = document.getElementById('lightbox');
const lightboxImg = document.getElementById('lightbox-img');

function openLightbox(gIndex, iIndex) {
  currentGallery = gIndex;
  currentIndex = iIndex;
  updateLightboxImage();
  lightbox.style.display = 'flex';
}

function closeLightbox() {
  lightbox.style.display = 'none';
}

function updateLightboxImage() {
  const gallery = galleries[currentGallery];
  lightboxImg.src = fullPath + gallery.folder + "/" + gallery.images[currentIndex];
}

function showNext() {
  const gallery = galleries[currentGallery];
  currentIndex = (currentIndex + 1) % gallery.images.length;
  updateLightboxImage();
}

function showPrev() {
  const gallery = galleries[currentGallery];
  currentIndex = (currentIndex - 1 + gallery.images.length) % gallery.images.length;
  updateLightboxImage();
}

document.getElementById('lightbox-close').addEventListener('click', closeLightbox);
document.getElementById('lightbox-next').addEventListener('click', showNext);
document.getElementById('lightbox-prev').addEventListener('click', showPrev);

lightbox.addEventListener('click', (e) => {
  if (e.target === lightbox) closeLightbox();
});

document.addEventListener('keydown', (e) => {
  if (lightbox.style.display !== 'flex') return;
  if (e.key === 'Escape') closeLightbox();
  if (e.key === 'ArrowRight') showNext();
  if (e.key === 'ArrowLeft') showPrev();
});
</script>
