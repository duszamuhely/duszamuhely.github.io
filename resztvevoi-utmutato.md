---
layout: doc
title: Résztvevői útmutató
subtitle: A Dusza Árpád Programozóműhely működése, szabályai és elvárásai
frissitve: "2026. szeptember 25."
permalink: /resztvevoi-utmutato/
---

Jelen dokumentum célja a Dusza Árpád Programozóműhely elnevezésű, középiskolásoknak szóló informatikai tehetséggondozó program bemutatása. A leírás tartalmazza a program célját, felépítését és a résztvevőkkel szemben támasztott elvárásokat, definiált feladatokat.

A programozóműhely gondozója az Informatika-Számítástechnikatanárok Egyesülete (ISZE). Szervezője és társszervezője az ISZE és az ELTE Informatikai Kara.

## Célkitűzés

A programozóműhely azoknak a középiskolás csapatoknak szól, akik saját szoftverötletüket szeretnék megvalósítani az iparban dolgozó mentorok támogatásával, akik az alábbi területeken segítik az induló csapatokat:

* **Szakmai fejlődés:** kódminőség, architektúra, verziókezelés, code review, tesztelés, valamint a mesterséges intelligencia (AI) tudatos és ellenőrzött használata. Az AI a tanulást és a munkát segíti, nem helyettesíti azokat.
* **Csapatmunka kialakítása:** a felelősségek egyértelmű elosztása és a közös munka szervezése.
* **Projektmenedzsment szemlélet megalapozása:** tervezés, a feladatok ütemezése és követése, a terv és a valóság közötti eltérések kezelése.
* **Prezentációs és kommunikációs készségek fejlesztése:** a projekt állapotának, döntéseinek és eredményeinek érthető, időkeretre szabott bemutatása és a kérdések megválaszolása.

A műhely célja nem az érettségire való felkészítés és nem a programozás tanítása. Ezért a csapatoktól már a jelentkezéskor elvárjuk, hogy tudjanak működő programot írni.

A program két személyes workshopból és egy záró eseményből áll. **Minden alkalmon működő szoftvert kell bemutatni.** A bemutatót kidolgozott, begyakorolt prezentáció keretezi, amely a szoftver fejlődését követi alkalomról alkalomra. A workshopokon a mentorok az ott látottak alapján döntenek a csapatok továbbhaladásáról.
{: .callout}

A műhely elvárásai mindenkire egyformán kötelezők: a mérföldkövek teljesítését minden csapatnak a workshopokon kell bizonyítania.

## A részvétel feltételei

Olyan csapatok jelentkezését várjuk, amelyeknek tagjai **alapszinten már tudnak programozni** (képesek a választott programozási nyelvben/technológiában felhasználói felülettel rendelkező alkalmazásokat implementálni), és **vállalják, hogy az általuk választott technológiákban önállóan elmélyednek**, miközben a mentoruk iránymutatást nyújt számukra a felmerülő problémák megoldása során. Elvárjuk, hogy a jelentkező csapatok legalább egyik tagja jól tudjon programozni. Ugyanakkor fontos, hogy a csapat összetétele arányos legyen: nagyobb létszám esetén nem elegendő, ha kizárólag egy ember rendelkezik programozói tudással.

* Csapatlétszám: 3–5 fő
* A workshopokon és a záró eseményen a részvétel kötelező, ettől eltérni csak nagyon indokolt esetben lehet.

A jelentkezés menetéről és a kiválasztás szempontjairól a [főoldalon](/#hogyan-jelentkezz) tájékozódhatnak.

## Mérföldkövek

A program két workshopból és egy záró eseményből áll.

<ol class="flow">
  <li><strong>1. workshop</strong><span>A vállalt funkciók működő része, tervek a többihez, a prezentáció első változata</span></li>
  <li><strong>2. workshop</strong><span>A fő funkció működik, a prezentáció közel végleges</span></li>
  <li class="is-final"><strong>Záró esemény</strong><span>Önállóan futtatható, teljes megoldás és kész prezentáció a közönség előtt</span></li>
</ol>

A csapat a mentorával közösen **mérföldkő-tervet** készít, amely megadja, melyik funkció várhatóan melyik alkalomra készül el (1. workshop, 2. workshop, záró esemény). A tervet az 1. és a 2. workshop előtt a mentorral együtt aktualizálják a tényleges haladás szerint. Mindig az aktuális terv a következő alkalom mércéje.

**A workshopok célja,** hogy a csapatok megmutassák a mentoroknak és a többi csapatnak, hogyan haladtak a projektjükkel: minden alkalommal működő szoftvert mutatnak be, amely az előző alkalomhoz képest továbbfejlődött. A bemutatót strukturált prezentáció keretezi, amely a szoftverrel együtt fejlődik: első változata az 1. workshopra készül el, a 2. workshopra a szoftver aktuális állapotához igazodik, végső formáját pedig a záró eseményen látja a közönség. A workshopok arra is lehetőséget adnak, hogy a csapatok megosszák egymással a tapasztalataikat, és tanuljanak egymástól.

A workshopokon a mentorok és a résztvevők kérdéseket tesznek fel, és visszajelzéseket adnak a csapatoknak.

A workshopokkal, a záró eseménnyel és a prezentációval kapcsolatos részletes elvárásokat a [Teljesítési kritériumok](#teljesitesi-kriteriumok) fejezet tartalmazza.

### Kapcsolatfelvétel és kapcsolattartás a mentorral

A mentor támogatást nyújt a csapatnak. Segít a tervezésben, a felmerülő problémák megoldásában és az eszközök használatában, visszajelzést ad a prezentációra, és jelzi, ha a haladás nem megfelelő. A felkészítő tanárral együtt támogatja a csapatmunkát is: segít kialakítani a tagok közötti munkamegosztást, és figyel arra, hogy minden csapattag érdemben részt vegyen a munkában. Megállapodás szerint részt vehet támogató feladatokban (például code review, páros programozás, tesztelés), de az implementációt teljes egészében a csapatnak kell elvégeznie.

A kiválasztás után, az 1. workshop előtt a mentor felveszi a kapcsolatot a csapattal. Ekkor közösen:

* a mentor tisztázza a csapattal az egyes workshopok és a záróesemény céljait,
* elkészítik a mérföldkő-tervet,
* beállítják a Git-repót, a mentor hozzáférésével,
* megállapodnak a feladatkövető rendszerben, és beállítják azt (ajánlott: Trello); a feladatkövetőben minden csapattag és a mentor számára átlátható lesz, hogy milyen feladatokat tervezett a csapat, és melyiken épp ki dolgozik,
* egyeztetik a heti kapcsolattartás csatornáját és időpontját (ajánlott: Discord).

A workshopok között a csapatoknak a megállapodott feladatokon kell dolgozniuk, melyek állapotát folyamatosan egyeztetik mentorukkal, aki szükség esetén, a csapat igényeihez alkalmazkodva tanácsot, segítséget ad a feladatok elvégzéséhez. **A csapat kötelessége jelezni, ha elakad,** és válaszolni a mentor kéréseire.

**A mentorral a műhely időtartama alatt a heti kapcsolattartás kötelező.** A heti meetingeken érdemi egyeztetés zajlik a csapat és a mentor között (esetlegesen a felkészítő tanár részvételével). A munka látható a repóban és a feladatkövetőben, és megoszlik a tagok között.
{: .callout}

Ha a program közben kiderül, hogy a csapat nem tud teljes létszámmal részt venni későbbi workshopon vagy a záró eseményen, a mentort erről mihamarabb értesíteni szükséges, aki a program vezetőjével egyeztet a fennálló helyzetről, és annak lehetséges áthidalásáról.

A mentorral való közös munkában minden csapattag részt vesz. Nem megfelelő módszer, ha csak egy csapattag egyeztet a mentorral és továbbítja az információkat, illetve az sem megfelelő, ha egy-egy kérdésre, kérésre csak napokkal később érkezik válasz, mert a felek ritkán olvassák el az üzeneteket.

### 1. workshop

Az 1\. workshopon a csapatok, a felkészítő tanárok és a mentorok vesznek részt. A csapat bemutatja, amit eddig elkészített: a szoftver működő részét, valamint a még el nem készült részek terveit, például képernyőterveket vagy a backend architektúratervét. Ekkor mutatja be a prezentáció első változatát is. A bemutató után a mentorok visszajelzést adnak és kérdéseket tesznek fel, és a többi csapat is kérdezhet. A csapat fogadja a visszajelzéseket, és megválaszolja a kérdéseket. A workshopon a csapatok és mentoruk lehetőséget kapnak a személyes közös munkára.

### 2. workshop

A 2\. workshop az elsőhöz hasonlóan zajlik. Itt már elvárás, hogy a szoftver fő funkcionalitása működjön. A prezentáció a szoftver aktuális állapotát mutatja be, és már közel áll a végleges formájához. A bemutatót ismét visszajelzés és kérdések követik. A workshopon a csapatok és mentoruk ismét lehetőséget kapnak a személyes közös munkára.

### Záró esemény

A záró eseményen a közönség teljes megoldást lát (a rendelkezésre álló időtartam figyelembevételével). A csapatokon, a felkészítő tanárokon és a mentorokon kívül a csapattagok hozzátartozói és szakmai érdeklődők is jelen lesznek. A csapat összeveti az eredményt a jelentkezéskor kitűzött céljaival. A programot sikeresen teljesítő csapatok oklevelet kapnak.

### Továbbhaladás

Ha a program során a mentor úgy látja, hogy a csapat nem teljesíti a műhely elvárásait (workshopok teljesítési kritériumai, prezentáció teljesítési kritériumai, heti szintű egyeztetések mennyisége és minősége, a csapat teljesítménye, a csapattal kötött megállapodások betartása), bevonja a program vezetőjét és a felkészítő tanárt (amennyiben ő is aktívan részt vesz a programban) a kialakult helyzet tisztázásába. A mentor, a felkészítő tanár, a program vezetője és a csapat közösen megállapodnak a helyzet megoldásáról. Ha nem sikerül megoldást találni vagy a csapat a későbbiekben nem teljesíti a megállapodásokat, a program vezetője megszakítja a csapat programban való részvételét.

## Felkészítő tanár

A csapatoknak a jelentkezéskor meg kell jelölniük felkészítő tanárukat is, akinek szintén fontos szerep jut a program során. Eddigi tapasztalataink szerint a felkészítő tanár jelenléte és tevékenysége nagyban meghatározza a diákok sikeres csapatként való együttműködését, és hatékonyan tudja támogatni a csapatot a következőkben:

* Amennyiben a csapattagok között problémák, viták merülnek fel, segíti őket ezek megoldásában, hogy a diákok valódi csapatként dolgozhassanak együtt.
* A mentorhoz hasonlóan figyeli a csapat munkáját, visszajelzést ad nekik, biztatja őket, segít nekik a felmerülő akadályok elhárításában.
* A workshopokra támogatja, segíti a felkészülést, például azzal, hogy a workshop előtt meghallgatja a csapat prezentációját, és visszajelzést ad róla.
* A feladatokhoz szükséges feltételeket biztosítja (például az iskolában helyet, számítógépet a munkához, ha a csapatnak szüksége van rá).
* Szervezi a csapat utazását a workshopok és a záró esemény során, valamint ha plusz személyes találkozót egyeztet a csapat és a mentor, akkor segít a helyszín biztosításában (például az iskolában).
* Az iskolavezetéssel egyeztet a szükséges utazásokról és egyéb biztosítandó dolgokról, és ehhez támogatást kér.
* A workshopokra elkíséri a csapatot, és ott aktívan segíti őket visszajelzéssel, kérdésekkel.

A korábbi évek tapasztalatai alapján azt kérjük, hogy amennyiben megoldható, a diákok aktuális informatikatanára/digitális kultúra tanára legyen a felkészítő tanár. Mivel ő napi kapcsolatban van a diákokkal, nagyobb valószínűséggel tud majd nekik segíteni abban, hogy a projektmunka útjában álló napi akadályok elhárításra kerüljenek.

## Teljesítési kritériumok

### 1. workshop

- [ ] Az 1\. workshopra vállalt funkciók részben vagy teljes egészében működnek, amit élőben be is mutat a csapat.
- [ ] A szoftver még el nem készült részeihez tervek tartoznak (például képernyőtervek, architektúraterv).
- [ ] A prezentáció első változata minden fejezetet tartalmaz. A még meg nem valósult részek tervként szerepelnek.
- [ ] A prezentációban a csapat aktualizálta a mérföldkő-tervet (2. workshop, záró esemény), és az reális.
- [ ] A prezentálásban mindenki érdemben részt vesz.
- [ ] A prezentáció begyakorolt.

### 2. workshop

- [ ] A program fő funkciója működik, amit élőben bemutat a csapat.
- [ ] A prezentáció az aktuális állapotot mutatja be, és beépíti az 1\. workshopon kapott visszajelzéseket.
- [ ] A prezentáció minél közelebb áll a végleges állapothoz.
- [ ] A prezentációban a csapat aktualizálta a mérföldkő-tervet (záróesemény), és az reális.
- [ ] A prezentálásban mindenki érdemben részt vesz.
- [ ] A prezentáció begyakorolt.

### Záró esemény

- [ ] A szoftvernek a fejlesztői környezettől (IDE) függetlenül, önállóan futtathatónak és telepíthetőnek kell lennie.
- [ ] A fő felhasználási esetek hiba nélkül bemutathatók (vagy élő demóban vagy előre rögzített videóban).
- [ ] A prezentáció kész és begyakorolt.
- [ ] A csapat összeveti az eredményt a jelentkezéskor kitűzött céljaival, és reflektál rá.

### A prezentáció szerkezete

A prezentációnak tartalmilag az alábbi pontokat kell lefednie. Ezeken felül a csapat bármit beletehet, amit a projektjével kapcsolatban fontosnak tart. A pontok sorrendje és az egyes részek aránya a csapatra van bízva.

- [ ] Csapatbemutatkozás
- [ ] Az ötlet: célfelhasználók, probléma
- [ ] Élő demó
- [ ] Technológiai stack és architektúra
- [ ] Minőség: tesztelés, code review, AI-használat
- [ ] Csapatmunka: ki min dolgozott
- [ ] Projektterv és megvalósulása, változások, tanulságok
- [ ] Hogyan tovább
- [ ] A prezentáció nem haladja meg a 10 percet (záróesemény).
