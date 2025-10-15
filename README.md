# The QUEST
Projekt sa zaoberá predikovaním závislých hodnôt premennej **oximetry (predikovaná premenná)** pomocou metód strojového učenia.

#### Očakavaný výstup projektu:
1. najlepší model strojového učenia 
2. data pipeline pre jeho vybudovanie na základe vstupných dát

### Authors
- Johanna Tilešová [@JohannaTilesova](https://github.com/johannatilesova)
- Adam Pečenka [@AdamPecenka](https://github.com/AdamPecenka)

## 1. fáza - prieskumná analýza
### 1.1 Základný opis dát spolu s ich charakteristikami
EDA s vizualizáciou
- [ ] Analýza štruktúr dát ako súbory (štruktúry a vzťahy, počet, typy, …), záznamy (štruktúry, počet záznamov, počet atribútov, typy, …)
- [ ] Analýza jednotlivých atribútov: pre zvolené významné atribúty (min 10) analyzujte ich distribúcie a základné deskriptívne štatistiky a či spĺňa predpísané podmienky a rozsah meraných hodnôt. 
- [ ] Párová analýza dát: Identifikujte vzťahy a závislostí medzi dvojicami atribútov.
- [ ] Párová analýza dát: Identifikujte závislosti medzi predikovanou premennou a ostatnými premennými (potenciálnymi prediktormi).
- [ ] Dokumentujte Vaše prvotné zamyslenie k riešeniu zadania projektu, napr. sú niektoré atribúty medzi sebou závislé? od ktorých atribútov závisí predikovaná premenná? či je potrebné kombinovať záznamy z viacerých súborov? 

### 1.2 Identifikácia problémov, integrácia a čistenie dát
- [ ] Identifikujte aj prvotne riešte problémy v dátach napr.: nevhodná štruktúra dát, duplicitné záznamy, ktoré môžu vznikať po určitých dátových transformáciach, nejednotné formáty, chýbajúce hodnoty, vychýlené hodnoty. V dátach sa môžu nachádzať aj iné, tu nevymenované problémy, resp. menej problémov ako bolo uvedených.
- [ ] Kontrola správnosť v dátach 
  - či obsahujú abnormálne hodnoty 
  - či obsahujú nelogické dátové vzťahy, ktoré sú následkom dátovej kolekcie a anotovania dát
- [ ] Vychýlené hodnoty (outlier detection), vyskúšajte riešiť problém min. 2 technikami 
  - odstránenie vychýlených alebo odľahlých pozorovaní 
  - nahradenie vychýlenej hodnoty hraničnými hodnotami rozdelenia (napr. 5%, 95%)

### 1.3 Formulácia a štatistické overenie hypotéz o dátach
- [ ] Sformulujte dve hypotézy o dátach v kontexte zadanej predikčnej úlohy. Formulované hypotézy overte vhodne zvolenými štatistickými testami.
  - _(SK) FiO₂ má v priemere vyššiu hodnotu v stave s oximetry ako bez nej._
  - _(EN) FiO₂ has, on average, a higher value in the state with oximetry than without it._
- [ ] Overte či Vaše štatistické testy majú dostatok podpory z dát, teda či majú dostatočne silnú štatistickú silu.

## 2. fáza - Predspracovanie údajov 

## 3. fáza - Strojové učenie