---
layout: page
title: Galéria
permalink: /galeria/
---

<style>
.gallery-section { margin: 0 0 3.5rem; }
.gallery-head {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 0.5rem 1rem;
  flex-wrap: wrap;
  margin-bottom: 0.9rem;
}
.gallery-head h2 { margin: 0; font-size: clamp(1.2rem, 2.2vw, 1.5rem); }
.gallery-count { color: var(--ink-soft); font-size: 0.95rem; }

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(var(--cols, 4), 1fr);
  gap: 10px;
}
.gallery-grid button {
  padding: 0;
  border: 0;
  background: var(--mint);
  border-radius: 8px;
  overflow: hidden;
  cursor: zoom-in;
  aspect-ratio: 4 / 3;
}
.gallery-grid img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.2s ease;
}
.gallery-grid button:hover img { transform: scale(1.04); }
.gallery-grid button:focus-visible { outline: 3px solid var(--orange); outline-offset: 2px; }

.gallery-pager {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  margin-top: 0.9rem;
}
.gallery-pager button {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 50%;
  border: 2px solid var(--green-deep);
  background: transparent;
  color: var(--ink);
  font-size: 1.4rem;
  line-height: 1;
  cursor: pointer;
}
.gallery-pager button:hover:not(:disabled) { background: var(--green-deep); color: #fff; }
.gallery-pager button:disabled { opacity: 0.3; cursor: default; }
.gallery-pager .page-info { min-width: 4.5rem; text-align: center; font-variant-numeric: tabular-nums; color: var(--ink-soft); }

/* Lightbox */
#lightbox {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(10, 20, 17, 0.94);
  align-items: center;
  justify-content: center;
  z-index: 999;
  touch-action: pan-y;
}
#lightbox.is-open { display: flex; }
#lightbox img {
  max-width: 88%;
  max-height: 84%;
  border-radius: 4px;
  user-select: none;
}
#lightbox-close {
  position: absolute; top: 16px; right: 20px;
  color: #fff; font-size: 2.4rem; line-height: 1;
  background: none; border: none; cursor: pointer;
}
.lightbox-nav {
  position: absolute; top: 50%; transform: translateY(-50%);
  color: #fff; font-size: 2.5rem; line-height: 1;
  background: rgba(255,255,255,0.08); border: none;
  width: 3.25rem; height: 3.25rem; border-radius: 50%;
  cursor: pointer;
}
.lightbox-nav:hover, #lightbox-close:hover { background: rgba(255,255,255,0.18); }
#lightbox-close { border-radius: 50%; width: 3rem; height: 3rem; }
#lightbox-prev { left: 16px; }
#lightbox-next { right: 16px; }
#lightbox-caption {
  position: absolute; bottom: 16px; left: 0; right: 0;
  text-align: center; color: #cfe0d8; font-size: 0.95rem;
  padding: 0 1rem;
}
@media (max-width: 600px) {
  .lightbox-nav { width: 2.6rem; height: 2.6rem; font-size: 2rem; }
  #lightbox img { max-width: 100%; }
}
</style>

<div id="galleries-container"></div>

<div id="lightbox" role="dialog" aria-modal="true" aria-label="Kép nagyítva">
  <button id="lightbox-close" aria-label="Bezárás">&times;</button>
  <button class="lightbox-nav" id="lightbox-prev" aria-label="Előző kép">&#8249;</button>
  <img id="lightbox-img" src="" alt="">
  <button class="lightbox-nav" id="lightbox-next" aria-label="Következő kép">&#8250;</button>
  <div id="lightbox-caption"></div>
</div>

<script>
// A galériák adatai: cím, mappa, fájlnevek.
// Bélyegképek: assets/gallery/thumbs/<folder>/<fájl>, eredetik: assets/gallery/full/<folder>/<fájl>
const galleries = [
  {
    title: "Dusza Műhely Zárórendezvény (2026. február 14.)",
    folder: "20260214",
    images: [
      "02_wp_IMG_7506.jpg",
      "05_wp_IMG_7503.jpg",
      "08_wp_IMG_7500.jpg",
      "11_wp_IMG_7497.jpg",
      "14_wp_IMG_7494.jpg",
      "18_wp_IMG_7490.jpg",
      "20_wp_IMG_7488.jpg",
      "22_wp_IMG_7486.jpg",
      "25_wp_IMG_7483.jpg",
      "32_wp_IMG_7476.jpg",
      "33_wp_IMG_7475.jpg",
      "39_wp_IMG_7469.jpg",
      "41_wp_IMG_7467.jpg",
      "42_wp_IMG_7466.jpg",
      "43_wp_IMG_7465.jpg",
      "44_wp_IMG_7464.jpg",
      "48_wp_IMG_7460.jpg",
      "50_wp_IMG_7458.jpg",
      "51_wp_IMG_7457.jpg",
      "55_wp_IMG_7453.jpg",
      "60_wp_IMG_7448.jpg",
      "61_wp_IMG_7447.jpg",
      "65_wp_IMG_7443.jpg",
      "67_wp_IMG_7441.jpg",
      "68_wp_IMG_7440.jpg",
      "69_wp_IMG_7439.jpg",
      "71_wp_IMG_7437.jpg",
      "72_wp_IMG_7436.jpg",
      "74_wp_IMG_7434.jpg",
      "79_wp_IMG_7430.jpg",
      "80_wp_IMG_7429.jpg",
      "85_wp_IMG_7424.jpg",
      "86_wp_IMG_7423.jpg",
      "87_wp_IMG_7422.jpg",
      "89_wp_IMG_7419.jpg",
      "94_wp_IMG_7414.jpg",
      "96_wp_IMG_7412.jpg",
      "98_wp_IMG_7410.jpg",
      "100_wp_IMG_7408.jpg",
      "102_wp_IMG_7406.jpg",
      "105_wp_IMG_7403.jpg",
      "107_wp_IMG_7401.jpg",
      "110_wp_IMG_7398.jpg",
      "113_wp_IMG_7395.jpg",
      "116_wp_IMG_7392.jpg",
      "121_wp_IMG_7387.jpg",
      "124_wp_IMG_7384.jpg",
      "125_wp_IMG_7383.jpg",
      "131_wp_IMG_7377.jpg",
      "132_wp_IMG_7376.jpg",
      "134_wp_IMG_7374.jpg",
      "135_wp_IMG_7373.jpg",
      "136_wp_IMG_7372.jpg",
      "138_wp_IMG_7370.jpg",
      "139_wp_IMG_7369.jpg",
      "140_wp_IMG_7368.jpg",
      "141_wp_IMG_7367.jpg",
      "144_wp_IMG_7364.jpg",
      "145_wp_IMG_7363.jpg",
      "148_wp_IMG_7360.jpg",
      "150_wp_IMG_7358.jpg",
      "151_wp_IMG_7357.jpg",
      "154_wp_IMG_7354.jpg",
      "155_wp_IMG_7353.jpg",
      "157_wp_IMG_7351.jpg",
      "160_wp_IMG_7348.jpg",
      "162_wp_IMG_7346.jpg",
      "163_wp_IMG_7345.jpg",
      "164_wp_IMG_7344.jpg",
      "165_wp_IMG_7343.jpg",
      "166_wp_IMG_7342.jpg",
      "167_wp_IMG_7341.jpg",
      "168_wp_IMG_7340.jpg",
      "169_wp_IMG_7339.jpg",
      "173_wp_IMG_7335.jpg",
      "175_wp_IMG_7333.jpg",
      "176_wp_IMG_7332.jpg",
      "180_wp_IMG_7328.jpg",
      "182_wp_IMG_7326.jpg",
      "184_wp_IMG_7324.jpg",
      "186_wp_IMG_7322.jpg",
      "188_wp_IMG_7320.jpg",
      "189_wp_IMG_7319.jpg",
      "191_wp_IMG_7317.jpg"
    ]
  },
  {
    title: "Dusza Műhely Zárórendezvény (2025. február 22.)",
    folder: "20250222",
    images: [
      "IMG_8522-masolat.webp",
      "IMG_8529-masolat.webp",
      "IMG_8533-masolat.webp",
      "IMG_8539-masolat.webp",
      "IMG_8542-masolat.webp",
      "IMG_8544-masolat.webp",
      "IMG_8547-masolat.webp",
      "IMG_8549-masolat.webp",
      "IMG_8555-masolat.webp",
      "IMG_8556-masolat.webp",
      "IMG_8558-masolat.webp",
      "IMG_8571-masolat.webp",
      "IMG_8574-masolat.webp",
      "IMG_8577-masolat.webp",
      "IMG_8579-masolat.webp",
      "IMG_8584-masolat.webp",
      "IMG_8588-masolat.webp",
      "IMG_8590-masolat.webp",
      "IMG_8597-masolat.webp",
      "IMG_8600-masolat.webp",
      "IMG_8603-masolat.webp",
      "IMG_8607-masolat.webp",
      "IMG_8609-masolat.webp",
      "IMG_8613-masolat.webp",
      "IMG_8617-masolat.webp",
      "IMG_8618-masolat.webp",
      "IMG_8619-masolat.webp",
      "IMG_8627-masolat.webp",
      "IMG_8628-masolat.webp",
      "IMG_8632-masolat.webp",
      "IMG_8638-masolat.webp",
      "IMG_8640-masolat.webp",
      "IMG_8641-masolat.webp",
      "IMG_8646-masolat.webp",
      "IMG_8647-masolat.webp",
      "IMG_8649-masolat.webp",
      "IMG_8654-masolat.webp",
      "IMG_8656-masolat.webp",
      "IMG_8657-masolat.webp",
      "IMG_8659-masolat.webp",
      "IMG_8660-masolat.webp",
      "IMG_8663-masolat.webp",
      "IMG_8669-masolat.webp",
      "IMG_8678-masolat.webp",
      "IMG_8680-masolat.webp",
      "IMG_8683-masolat.webp",
      "IMG_8687-masolat.webp",
      "IMG_8689-masolat.webp",
      "IMG_8692-masolat.webp",
      "IMG_8695-masolat.webp",
      "IMG_8696-masolat.webp",
      "IMG_8700-masolat.webp",
      "IMG_8701-masolat.webp",
      "IMG_8706-masolat.webp",
      "IMG_8711-masolat.webp",
      "IMG_8714-masolat.webp",
      "IMG_8717-masolat.webp",
      "IMG_8718-masolat.webp",
      "IMG_8722-masolat.webp",
      "IMG_8725-masolat.webp",
      "IMG_8729-masolat.webp",
      "IMG_8731-masolat.webp",
      "IMG_8732-masolat.webp",
      "IMG_8736-masolat.webp",
      "IMG_8737-masolat.webp",
      "IMG_8738-masolat.webp",
      "IMG_8739-masolat.webp",
      "IMG_8740-masolat.webp",
      "IMG_8744-masolat.webp",
      "IMG_8748-masolat.webp",
      "IMG_8751-masolat.webp",
      "IMG_8753-masolat.webp",
      "IMG_8754-masolat.webp",
      "IMG_8756-masolat.webp",
      "IMG_8763-masolat.webp",
      "IMG_8766-masolat.webp",
      "IMG_8767-masolat.webp",
      "IMG_8771-masolat.webp",
      "IMG_8773-masolat.webp",
      "IMG_8774-masolat.webp",
      "IMG_8775-masolat.webp",
      "IMG_8778-masolat.webp",
      "IMG_8779-masolat.webp",
      "IMG_8783-masolat.webp",
      "IMG_8786-masolat.webp",
      "IMG_8788-masolat.webp",
      "IMG_8790-masolat.webp",
      "IMG_8791-masolat.webp",
      "IMG_8793-masolat.webp",
      "IMG_8795-masolat.webp",
      "IMG_8799-masolat.webp",
      "IMG_8801-masolat.webp",
      "IMG_8802-masolat.webp",
      "IMG_8803-masolat.webp",
      "IMG_8804-masolat.webp",
      "IMG_8807-masolat.webp",
      "IMG_8809-masolat.webp",
      "IMG_8811-masolat.webp",
      "IMG_8814-masolat.webp",
      "IMG_8817-masolat.webp",
      "IMG_8818-masolat.webp",
      "IMG_8819-masolat.webp",
      "IMG_8821-masolat.webp",
      "IMG_8824-masolat.webp",
      "IMG_8825-masolat.webp",
      "IMG_8831-masolat.webp",
      "IMG_8832-masolat.webp",
      "IMG_8834-masolat.webp",
      "IMG_8840-masolat.webp",
      "IMG_8843-masolat.webp",
      "IMG_8847-masolat.webp",
      "IMG_8848-masolat.webp",
      "IMG_8849-masolat.webp",
      "IMG_8851-masolat.webp",
      "IMG_8856-masolat.webp",
      "IMG_8858-masolat.webp",
      "IMG_8859-masolat.webp",
      "IMG_8863-masolat.webp",
      "IMG_8866-masolat.webp",
      "IMG_8867-masolat.webp",
      "IMG_8873-masolat.webp",
      "IMG_8877-masolat.webp",
      "IMG_8882-masolat.webp",
      "IMG_8886-masolat.webp",
      "IMG_8890-masolat.webp",
      "IMG_8896-masolat.webp",
      "IMG_8899-masolat.webp",
      "IMG_8901-masolat.webp",
      "IMG_8902-masolat.webp",
      "IMG_8905-masolat.webp",
      "IMG_8906-masolat.webp",
      "IMG_8910-masolat.webp",
      "IMG_8912-masolat.webp",
      "IMG_8918-masolat.webp",
      "IMG_8921-masolat.webp",
      "IMG_8927-masolat.webp",
      "IMG_8929-masolat.webp",
      "IMG_8930-masolat.webp",
      "IMG_8936-masolat.webp",
      "IMG_8939-masolat.webp",
      "IMG_8941-masolat.webp",
      "IMG_8947-masolat.webp",
      "IMG_8952-masolat.webp",
      "IMG_8955-masolat.webp",
      "IMG_8961-masolat.webp",
      "IMG_8965-masolat.webp",
      "IMG_8976-masolat.webp",
      "IMG_8982-masolat.webp",
      "IMG_8988-masolat.webp",
      "IMG_8994-masolat.webp",
      "IMG_8996-masolat.webp",
      "IMG_9002-masolat.webp",
      "IMG_9007-masolat.webp",
      "IMG_9008-masolat.webp",
      "IMG_9500-masolat.webp"
    ]
  },
  {
    title: "Dusza Műhely Zárórendezvény (2024. február 24.)",
    folder: "20240224",
    images: [
      "Dusza-Zarorendezveny1.webp",
      "Dusza-Zarorendezveny2.webp",
      "Dusza-Zarorendezveny3.webp",
      "Dusza-Zarorendezveny4.webp",
      "Dusza-Zarorendezveny5.webp",
      "Dusza-Zarorendezveny6.webp",
      "Dusza-Zarorendezveny7.webp",
      "Dusza-Zarorendezveny8.webp",
      "Dusza-Zarorendezveny9.webp",
      "Dusza-Zarorendezveny10.webp",
      "Dusza-Zarorendezveny11.webp",
      "Dusza-Zarorendezveny12.webp",
      "Dusza-Zarorendezveny13.webp",
      "Dusza-Zarorendezveny15.webp",
      "Dusza-Zarorendezveny16.webp",
      "Dusza-Zarorendezveny17.webp",
      "Dusza-Zarorendezveny18.webp",
      "Dusza-Zarorendezveny19.webp",
      "Dusza-Zarorendezveny20.webp",
      "Dusza-Zarorendezveny21.webp",
      "Dusza-Zarorendezveny23.webp",
      "Dusza-Zarorendezveny24.webp",
      "Dusza-Zarorendezveny25.webp",
      "Dusza-Zarorendezveny26.webp",
      "Dusza-Zarorendezveny27.webp",
      "Dusza-Zarorendezveny28.webp",
      "Dusza-Zarorendezveny29.webp",
      "Dusza-Zarorendezveny30.webp",
      "Dusza-Zarorendezveny32.webp",
      "Dusza-Zarorendezveny33.webp",
      "Dusza-Zarorendezveny34.webp",
      "Dusza-Zarorendezveny35.webp",
      "Dusza-Zarorendezveny36.webp",
      "Dusza-Zarorendezveny37.webp",
      "Dusza-Zarorendezveny38.webp",
      "Dusza-Zarorendezveny39.webp",
      "Dusza-Zarorendezveny40.webp",
      "Dusza-Zarorendezveny41.webp",
      "Dusza-Zarorendezveny42.webp",
      "Dusza-Zarorendezveny43.webp",
      "Dusza-Zarorendezveny44.webp",
      "Dusza-Zarorendezveny45.webp",
      "Dusza-Zarorendezveny46.webp",
      "Dusza-Zarorendezveny47.webp",
      "Dusza-Zarorendezveny48.webp",
      "Dusza-Zarorendezveny50.webp",
      "Dusza-Zarorendezveny51.webp",
      "Dusza-Zarorendezveny52.webp",
      "Dusza-Zarorendezveny53.webp",
      "Dusza-Zarorendezveny54.webp",
      "Dusza-Zarorendezveny55.webp",
      "Dusza-Zarorendezveny58.webp",
      "Dusza-Zarorendezveny59.webp",
      "Dusza-Zarorendezveny60.webp",
      "Dusza-Zarorendezveny61.webp",
      "Dusza-Zarorendezveny62.webp",
      "Dusza-Zarorendezveny63.webp",
      "Dusza-Zarorendezveny64.webp",
      "Dusza-Zarorendezveny65.webp",
      "Dusza-Zarorendezveny66.webp",
      "Dusza-Zarorendezveny67.webp",
      "Dusza-Zarorendezveny68.webp",
      "Dusza-Zarorendezveny70.webp",
      "Dusza-Zarorendezveny72.webp",
      "Dusza-Zarorendezveny74.webp",
      "Dusza-Zarorendezveny75.webp",
      "Dusza-Zarorendezveny76.webp",
      "Dusza-Zarorendezveny78.webp",
      "Dusza-Zarorendezveny80.webp",
      "Dusza-Zarorendezveny82.webp",
      "Dusza-Zarorendezveny84.webp",
      "Dusza-Zarorendezveny86.webp",
      "Dusza-Zarorendezveny88.webp"
    ]
  },
  {
    title: "Dusza Műhely az ELTE Nyílt Napon (2024. január 26.)",
    folder: "20240126",
    images: [
      "2TyEbplQ-–-nagy.jpeg",
      "7fjKRr4K-–-nagy.jpeg",
      "a5TSWluq-–-nagy.jpeg",
      "bHuPyMKM-–-nagy.jpeg",
      "CgDCBfoi-–-nagy.jpeg",
      "cZLRxz8b-–-nagy.jpeg",
      "EqKBM7bB-–-nagy.jpeg",
      "FmvnuFFI-–-nagy.jpeg",
      "MJXEaU0Y-–-nagy.jpeg",
      "NIAZgB42-–-nagy.jpeg",
      "NMLucz-g-–-nagy.jpeg",
      "OdiVF18Q-–-nagy.jpeg",
      "q6nxSKkQ-–-nagy.jpeg",
      "tera-eIX-–-nagy.jpeg",
      "TFXlgLAH-–-nagy.jpeg",
      "TpATDSDk-–-nagy.jpeg",
      "uEhhJ6mx-–-nagy.jpeg",
      "uHPIu74W-–-nagy.jpeg",
      "y8v4qx2x-–-nagy.jpeg",
      "zuMWNaPX-–-nagy.jpeg"
    ]
  },
  {
    title: "Dusza Műhely 3. workshop (2024. január 20.)",
    folder: "20240120",
    images: [
      "3-Dusza-workshop1.jpg",
      "3-Dusza-workshop2.jpg",
      "3-Dusza-workshop3.jpg",
      "3-Dusza-workshop4.jpg",
      "3-Dusza-workshop5.jpg",
      "3-Dusza-workshop6.jpg"
    ]
  },
  {
    title: "Dusza Műhely 2. workshop (2023. december 9.)",
    folder: "20231209",
    images: [
      "Dusza-workshop1.jpg",
      "Dusza-workshop2.jpeg",
      "Dusza-workshop3.jpeg",
      "Dusza-workshop4.jpeg",
      "Dusza-workshop5.jpeg",
      "Dusza-workshop6.jpeg",
      "Dusza-workshop7.jpeg",
      "Dusza-workshop8.jpeg",
      "Dusza-workshop9.jpg",
      "Dusza-workshop10.jpg",
      "Dusza-workshop11.jpg",
      "Dusza-workshop12.jpg",
      "Dusza-workshop13.jpg",
      "Dusza-workshop14.jpg",
      "Dusza-workshop15.jpg",
      "Dusza-workshop16.jpg",
      "Dusza-workshop17.jpg",
      "Dusza-workshop18.jpg",
      "Dusza-workshop19.jpg",
      "Dusza-workshop20.jpg",
      "Dusza-workshop21.jpg",
      "Dusza-workshop22.jpg",
      "Dusza-workshop23.jpg",
      "Dusza-workshop24.jpg",
      "Dusza-workshop25.jpg",
      "Dusza-workshop26.jpg",
      "Dusza-workshop27.jpg",
      "Dusza-workshop28.jpg",
      "Dusza-workshop29.jpg",
      "Dusza-workshop30.jpg",
      "Dusza-workshop31.jpg",
      "Dusza-workshop32.jpg",
      "Dusza-workshop33.jpg",
      "Dusza-workshop34.jpg",
      "Dusza-workshop35.jpg",
      "Dusza-workshop36.jpg",
      "Dusza-workshop37.jpg"
    ]
  }
];

const thumbsPath = "{{ '/assets/gallery/thumbs/' | relative_url }}";
const fullPath = "{{ '/assets/gallery/full/' | relative_url }}";
const ROWS = 2; // ennyi sor bélyegkép látszik egy oldalon

function src(base, g, file) { return base + g.folder + "/" + encodeURIComponent(file); }

// Oszlopszám a rendelkezésre álló szélesség alapján
function colsFor(width) {
  if (width < 420) return 2;
  if (width < 700) return 3;
  if (width < 1000) return 4;
  return 5;
}

const container = document.getElementById('galleries-container');
const views = [];

galleries.forEach((g, gi) => {
  const section = document.createElement('section');
  section.className = 'gallery-section';
  section.innerHTML =
    '<div class="gallery-head"><h2></h2><span class="gallery-count"></span></div>' +
    '<div class="gallery-grid"></div>' +
    '<div class="gallery-pager">' +
      '<button type="button" class="prev" aria-label="Előző oldal">&#8249;</button>' +
      '<span class="page-info" aria-live="polite"></span>' +
      '<button type="button" class="next" aria-label="Következő oldal">&#8250;</button>' +
    '</div>';
  section.querySelector('h2').textContent = g.title;
  section.querySelector('.gallery-count').textContent = g.images.length + ' kép';
  container.appendChild(section);

  const view = {
    g, gi, page: 0, perPage: 10,
    grid: section.querySelector('.gallery-grid'),
    pager: section.querySelector('.gallery-pager'),
    info: section.querySelector('.page-info'),
    prev: section.querySelector('.prev'),
    next: section.querySelector('.next')
  };
  view.prev.addEventListener('click', () => { view.page--; render(view); });
  view.next.addEventListener('click', () => { view.page++; render(view); });
  views.push(view);
});

function pages(v) { return Math.max(1, Math.ceil(v.g.images.length / v.perPage)); }

function render(v) {
  const cols = colsFor(v.grid.clientWidth || container.clientWidth);
  v.perPage = cols * ROWS;
  v.page = Math.min(Math.max(v.page, 0), pages(v) - 1);
  v.grid.style.setProperty('--cols', cols);
  v.grid.innerHTML = '';
  const start = v.page * v.perPage;
  v.g.images.slice(start, start + v.perPage).forEach((file, k) => {
    const i = start + k;
    const b = document.createElement('button');
    b.type = 'button';
    b.setAttribute('aria-label', v.g.title + ', ' + (i + 1) + '. kép megnyitása');
    const img = document.createElement('img');
    img.src = src(thumbsPath, v.g, file);
    img.alt = '';
    img.loading = 'lazy';
    b.appendChild(img);
    b.addEventListener('click', () => openLightbox(v, i));
    v.grid.appendChild(b);
  });
  const n = pages(v);
  v.pager.hidden = n < 2;
  v.info.textContent = (v.page + 1) + ' / ' + n;
  v.prev.disabled = v.page === 0;
  v.next.disabled = v.page >= n - 1;
}

views.forEach(render);
let resizeTimer;
window.addEventListener('resize', () => {
  clearTimeout(resizeTimer);
  resizeTimer = setTimeout(() => views.forEach(v => {
    // az oldal első képe maradjon látható átméretezés után is
    const first = v.page * v.perPage;
    render(v);
    v.page = Math.floor(first / v.perPage);
    render(v);
  }), 150);
});

// ---------- Lightbox ----------
const lightbox = document.getElementById('lightbox');
const lightboxImg = document.getElementById('lightbox-img');
const caption = document.getElementById('lightbox-caption');
let cur = null, idx = 0, lastFocus = null;

function openLightbox(v, i) {
  cur = v; idx = i; lastFocus = document.activeElement;
  show();
  lightbox.classList.add('is-open');
  document.body.style.overflow = 'hidden';
  document.getElementById('lightbox-close').focus();
}
function closeLightbox() {
  lightbox.classList.remove('is-open');
  document.body.style.overflow = '';
  // a rács arra az oldalra ugrik, ahol az utoljára nézett kép van
  if (cur) {
    const p = Math.floor(idx / cur.perPage);
    if (p !== cur.page) { cur.page = p; render(cur); }
  }
  if (lastFocus && document.contains(lastFocus)) lastFocus.focus();
}
function show() {
  const g = cur.g;
  lightboxImg.src = src(fullPath, g, g.images[idx]);
  lightboxImg.alt = g.title + ', ' + (idx + 1) + '. kép';
  caption.textContent = g.title + ' · ' + (idx + 1) + ' / ' + g.images.length;
  // a következő kép előtöltése
  const pre = new Image();
  pre.src = src(fullPath, g, g.images[(idx + 1) % g.images.length]);
}
function step(d) {
  const n = cur.g.images.length;
  idx = (idx + d + n) % n;
  show();
}

document.getElementById('lightbox-close').addEventListener('click', closeLightbox);
document.getElementById('lightbox-next').addEventListener('click', () => step(1));
document.getElementById('lightbox-prev').addEventListener('click', () => step(-1));
lightbox.addEventListener('click', e => { if (e.target === lightbox) closeLightbox(); });

document.addEventListener('keydown', e => {
  if (!lightbox.classList.contains('is-open')) return;
  if (e.key === 'Escape') closeLightbox();
  if (e.key === 'ArrowRight') step(1);
  if (e.key === 'ArrowLeft') step(-1);
});

// Lapozás húzással (telefonon)
let touchX = null;
lightbox.addEventListener('touchstart', e => { touchX = e.touches[0].clientX; }, { passive: true });
lightbox.addEventListener('touchend', e => {
  if (touchX === null) return;
  const dx = e.changedTouches[0].clientX - touchX;
  if (Math.abs(dx) > 50) step(dx < 0 ? 1 : -1);
  touchX = null;
});
</script>
