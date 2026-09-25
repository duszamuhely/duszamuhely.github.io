---
layout: default
title: Kezdőlap
---

<section class="hero wrap" id="jelentkezes">
  <div class="hero-art">
    <img src="{{ '/assets/img/hero-dusza.png' | relative_url }}" alt="Dusza Árpád Programozóműhely">
  </div>
  <div class="hero-text">
    <h1>Várjuk a jelentkezéseket a 2026–2027-es Dusza Műhelybe</h1>
    <p class="lead">3–5 fős középiskolás csapatok valósíthatják meg saját projektötletüket, iparban dolgozó mentorok támogatásával. 
    A részvétel ingyenes.<br>
    Nincs saját ötleted? <a href="{{ '/otletek/' | relative_url }}">Inspirálódj a projektötlet-listánkból.</a></p>
    <div class="hero-actions">
{% if site.jelentkezes_url != "" %}
      <a class="apply-btn apply-btn--lg" href="{{ site.jelentkezes_url }}" target="_blank" rel="noopener">Jelentkezés</a>
{% else %}
      <a class="apply-btn apply-btn--lg" href="#jelentkezes" data-apply>Jelentkezés</a>
{% endif %}
      <p>Határidő: <strong>2026. december 18.</strong></p>
    </div>
  </div>
</section>

<section class="season" aria-labelledby="season-title">
  <div class="wrap">
    <h2 id="season-title">Az évad időpontjai</h2>
    <ol class="timeline">
      <li class="is-deadline"><time datetime="2026-12-18"><small>2026.</small> december 18.</time><span>Jelentkezési határidő</span></li>
      <li><time datetime="2027-01-08"><small>2027.</small> január 8.</time><span>A mentorok döntenek a műhelybe jutó csapatokról</span></li>
      <li><time datetime="2027-01-30T09:00"><small>2027.</small> január 30.</time><span>I. workshop</span><span class="t-time">9:00–15:00</span></li>
      <li><time datetime="2027-02-20T09:00"><small>2027.</small> február 20.</time><span>II. workshop</span><span class="t-time">9:00–15:00</span></li>
      <li class="is-final"><time datetime="2027-03-21T10:00"><small>2027.</small> március 21.</time><span>Záróesemény</span><span class="t-time">10:00–12:00*</span></li>
    </ol>
    <div class="venue">
      <p><strong>A workshopok és a záróesemény helyszíne:</strong> ELTE Informatikai Kar, Budapest XI. kerület. A pontos helyszínt a résztvevők létszámától függően választjuk ki.</p>
      <p class="venue-note">* A záróesemény befejezésének időpontja a csapatok létszámától függően még változhat.</p>
    </div>
  </div>
</section>

<section class="apply-info wrap" id="hogyan-jelentkezz" aria-labelledby="apply-info-title">
  <h2 id="apply-info-title">Hogyan zajlik a jelentkezés?</h2>
  <p class="apply-info-lead">Középiskolás csapatokat várunk, akik már tudnak működő programot írni. A részletes feltételeket a <a href="{{ '/modszertani-utmutato/' | relative_url }}">módszertani útmutató</a> tartalmazza.</p>

  <div class="apply-grid">
    <div class="apply-card">
      <h3>Mit kell beküldeni?</h3>
      <ul>
        <li><strong>A csapat adatai:</strong> 3–5 fős csapat, a felkészítő tanár megjelölése kötelező.</li>
        <li><strong>A projektötlet bemutatása:</strong> írásos leírás (kb. egy A4-es oldal, de lehet több is), videó vagy prezentáció. Ötlet hiányában a <a href="{{ '/otletek/' | relative_url }}">projektötlet-listából</a> is lehet választani, és azt tetszőlegesen tovább lehet fejleszteni.</li>
        <li><strong>Mérföldkő-terv:</strong> melyik funkció várhatóan melyik alkalomra készül el (I. workshop, II. workshop, záróesemény).</li>
        <li><strong>Válaszok</strong> a jelentkezési űrlap kérdéseire.</li>
      </ul>
      <p class="apply-note">A workshopokon és a záróeseményen a csapatok részvétele kötelező. Ettől eltérni csak nagyon indokolt esetben lehet, ezt kérjük, jelezzétek a jelentkezéskor.</p>
    </div>

    <div class="apply-card apply-card--select">
      <h3>Hogyan választunk?</h3>
      <p>A jelentkezési időszak végén a mentorok döntenek a bejutó csapatokról. A döntés szempontjai:</p>
      <ul>
        <li>az ötlet kidolgozottsága,</li>
        <li>a projekt megvalósíthatósága a csapat programozási tapasztalatához mérten,</li>
        <li>részt tud-e venni a csapat a workshopokon és a záróeseményen,</li>
        <li>a rendelkezésre álló mentorálási kapacitás és a mentorok jártassága a választott technológiákban.</li>
      </ul>
      <p class="apply-quote">Nem a legjobb projektötletek vagy a legtapasztaltabb csapatok jutnak be, hanem azok, akiknél az összkép alapján a leghatékonyabb együttműködés várható a mentorokkal.</p>
      <p>A döntésről minden csapatot értesítünk, a bejutott csapatokkal pedig a hozzájuk kijelölt mentor veszi fel a kapcsolatot.</p>
    </div>
  </div>
</section>

<section class="rules wrap">
  <div class="rules-box">
    <h2>Idén változtak a szabályok</h2>
    <p>Az évadban két workshop és egy záróesemény lesz. Jelentkezés előtt a csapattagok és a felkészítő tanár is olvassa el a módszertani útmutatót, ebben minden részlet benne van.</p>
    <a href="{{ '/modszertani-utmutato/' | relative_url }}">Módszertani útmutató</a>
  </div>
</section>
