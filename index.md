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
{% include apply-button.html lg=true %}
      <p>Határidő: <strong>2026. december 18.</strong></p>
    </div>
    <p class="countdown" data-countdown="2026-12-18T23:59:59+01:00" hidden aria-live="polite"><span class="countdown-prompt" aria-hidden="true">&gt;</span> <span class="countdown-text"></span><span class="countdown-cursor" aria-hidden="true">_</span></p>
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
    <div class="section-cta">
      {% include apply-button.html lg=true %}
    </div>
  </div>
</section>

{% assign projektek = 0 %}{% assign iskolak = "" %}
{% for e in site.data.csapatok %}{% assign projektek = projektek | plus: e.csapatok.size %}{% for c in e.csapatok %}{% assign isk = c.iskola | split: ", " | first %}{% unless isk contains "Vegyes" %}{% assign iskolak = iskolak | append: isk | append: "|" %}{% endunless %}{% endfor %}{% endfor %}
{% assign iskolak = iskolak | split: "|" | uniq %}
{% assign mentorszam = site.mentorok_szama | default: site.data.mentorok.size %}
<section class="showcase wrap" aria-labelledby="showcase-title">
  <ul class="stats" aria-label="A műhely számokban">
    <li><strong data-count="{{ projektek }}">{{ projektek }}</strong><span>befejezett projekt</span></li>
    <li><strong data-count="{{ site.data.csapatok.size }}">{{ site.data.csapatok.size }}</strong><span>évad 2019 óta</span></li>
    <li><strong data-count="{{ iskolak.size }}">{{ iskolak.size }}</strong><span>iskola csapatai</span></li>
    <li><strong data-count="{{ mentorszam }}">{{ mentorszam }}</strong><span>mentor segítette a csapatokat</span></li>
  </ul>

  <div class="showcase-head">
    <h2 id="showcase-title">Ilyen projektek születtek</h2>
    <a href="{{ '/csapatok/' | relative_url }}">Az összes korábbi projekt</a>
  </div>
  <div class="project-cards" id="project-cards">
  {% assign elso = site.data.csapatok.first.csapatok %}
  {% for c in elso limit: 3 %}
    <article class="team-card">
      <h3>{% if c.nev %}{{ c.nev }}{% else %}{{ c.projekt }}{% endif %}</h3>
      {% if c.leiras %}<p class="team-desc">{{ c.leiras }}</p>{% endif %}
      <p class="project-meta">{{ c.iskola }} · {{ site.data.csapatok.first.evad }}</p>
      {% if c.tech %}<ul class="team-tech">{% for t in c.tech %}<li>{{ t }}</li>{% endfor %}</ul>{% endif %}
    </article>
  {% endfor %}
  </div>
  <script type="application/json" id="project-data">
  [{% for e in site.data.csapatok %}{% for c in e.csapatok %}{"cim": {{ c.nev | default: c.projekt | jsonify }}, "leiras": {{ c.leiras | jsonify }}, "projekt": {{ c.projekt | jsonify }}, "iskola": {{ c.iskola | jsonify }}, "evad": {{ e.evad | jsonify }}, "tech": {{ c.tech | jsonify }}}{% unless forloop.last %},{% endunless %}{% endfor %}{% unless forloop.last %},{% endunless %}{% endfor %}]
  </script>
</section>

<section class="apply-info wrap" id="hogyan-jelentkezz" aria-labelledby="apply-info-title">
  <h2 id="apply-info-title">Hogyan zajlik a jelentkezés?</h2>
  <p class="apply-info-lead">Középiskolás csapatokat várunk, akik már tudnak működő programot írni. <strong>Idén változtak a szabályok:</strong> az évadban két workshop és egy záróesemény lesz. Ezért ha korábban már részt vettetek a műhelyben, akkor is olvassátok el a felkészítő tanárotokkal együtt a <a href="{{ '/resztvevoi-utmutato/' | relative_url }}">résztvevői útmutatót</a>, amely a részletes feltételeket tartalmazza.</p>

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
  <div class="section-cta section-cta--final">
    {% include apply-button.html lg=true %}
  </div>
</section>
