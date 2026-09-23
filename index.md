---
layout: default
title: Kezdőlap
---

<section class="hero wrap">
  <div class="hero-art">
    <img src="{{ '/assets/img/hero-dusza.png' | relative_url }}" alt="Dusza Árpád Programozóműhely">
  </div>
  <div class="hero-text">
    <h1>Várjuk a jelentkezéseket a 2026–2027-es Dusza Műhelybe</h1>
    <p class="lead">3–5 fős középiskolás csapatok valósíthatják meg saját vagy választott projektötletüket, iparban dolgozó mentorok támogatásával. A részvétel ingyenes.</p>
    <div class="hero-actions">
{% if site.jelentkezes_url != "" %}
      <a class="btn" href="{{ site.jelentkezes_url }}" target="_blank" rel="noopener">Jelentkezem</a>
{% else %}
      <span class="btn is-disabled" aria-disabled="true">Az űrlap hamarosan nyílik</span>
{% endif %}
      <p>Határidő: <strong>2026. december 18.</strong></p>
    </div>
  </div>
</section>

<section class="season" aria-labelledby="season-title">
  <div class="wrap">
    <h2 id="season-title">Az évad időpontjai</h2>
    <ol class="timeline">
      <li class="is-deadline"><time datetime="2026-12-18">2026. december 18.</time><span>Jelentkezési határidő</span></li>
      <li><time datetime="2027-01-30">2027. január 30.</time><span>I. workshop</span></li>
      <li><time datetime="2027-02-20">2027. február 20.</time><span>II. workshop</span></li>
      <li class="is-final"><time datetime="2027-03-21">2027. március 21.</time><span>Záróesemény</span></li>
    </ol>
  </div>
</section>

<section class="rules wrap">
  <div class="rules-box">
    <h2>Idén változtak a szabályok</h2>
    <p>Az évadban két workshop és egy záróesemény lesz. Jelentkezés előtt a csapattagok és a felkészítő tanár is olvassa el a módszertani útmutatót, ebben minden részlet benne van.</p>
    <a href="{{ '/modszertani-utmutato/' | relative_url }}">Módszertani útmutató</a>
  </div>
</section>
