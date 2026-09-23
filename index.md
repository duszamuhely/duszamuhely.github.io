---
layout: default
title: Kezdőlap
---

<style>
.hero { text-align: center; margin: 1rem 0 2rem; }
.hero img { max-width: 420px; width: 100%; height: auto; }
.hero h1 { font-size: 1.9rem; margin: 1.2rem 0 0.4rem; line-height: 1.3; }
.hero .lead { font-size: 1.1rem; opacity: 0.85; max-width: 560px; margin: 0 auto; }

.dates { list-style: none; margin: 0; padding: 0; }
.dates li {
  display: flex; gap: 1rem; padding: 0.6rem 0;
  border-bottom: 1px solid rgba(128,128,128,0.25);
}
.dates li:last-child { border-bottom: none; }
.dates .d { font-weight: 700; min-width: 9.5rem; }
.dates .deadline .d, .dates .deadline .t { color: #c0392b; }

.notice {
  border-left: 4px solid #e67e22;
  background: rgba(230,126,34,0.08);
  padding: 0.9rem 1.1rem; border-radius: 4px; margin: 2rem 0;
}
.notice p { margin: 0; }

.cta { text-align: center; margin: 2.5rem 0 1rem; }
.btn {
  display: inline-block; padding: 0.8rem 2rem; border-radius: 6px;
  background: #2a7ae2; color: #fff !important; font-weight: 700;
  font-size: 1.1rem; text-decoration: none !important;
}
.btn:hover { background: #1f5fb4; }
.btn.disabled { background: #999; cursor: default; pointer-events: none; }
.cta small { display: block; margin-top: 0.5rem; opacity: 0.7; }

@media (max-width: 500px) {
  .hero h1 { font-size: 1.5rem; }
  .dates li { flex-direction: column; gap: 0.1rem; }
}
</style>

<div class="hero">
  <img src="{{ '/assets/img/hero-dusza.png' | relative_url }}" alt="Dusza Árpád Programozóműhely">
  <h1>Várjuk a jelentkezéseket a 2026–2027-es Dusza Műhelybe!</h1>
  <p class="lead">3–5 fős középiskolás csapatok valósíthatják meg saját vagy választott projektötletüket, iparban dolgozó mentorok támogatásával. A részvétel ingyenes.</p>
</div>

## Fontos időpontok

<ul class="dates">
  <li class="deadline"><span class="d">2026. december 18.</span><span class="t">jelentkezési határidő</span></li>
  <li><span class="d">2027. január 30.</span><span class="t">I. workshop</span></li>
  <li><span class="d">2027. február 20.</span><span class="t">II. workshop</span></li>
  <li><span class="d">2027. március 21.</span><span class="t">záróesemény</span></li>
</ul>

<div class="notice">
  <p><strong>Idén változtak a szabályok:</strong> két workshop és egy záróesemény lesz. Jelentkezés előtt a csapattagok és a felkészítő tanár is olvassa el a <a href="{{ '/modszertani-utmutato/' | relative_url }}">módszertani útmutatót</a>.</p>
</div>

<div class="cta">
{% if site.jelentkezes_url != "" %}
  <a class="btn" href="{{ site.jelentkezes_url }}" target="_blank" rel="noopener">Jelentkezés</a>
{% else %}
  <span class="btn disabled">Jelentkezés – hamarosan</span>
  <small>A jelentkezési űrlap hamarosan elérhető lesz.</small>
{% endif %}
</div>

<p style="text-align:center; opacity:0.7; font-size:0.9rem; margin-top:2.5rem;">
Szervező: Informatika-Számítástechnika Tanárok Egyesülete, az ELTE Informatikai Kar társszervezésében.<br>
Helyszín: ELTE Informatikai Kar, Budapest XI. kerület.
</p>
