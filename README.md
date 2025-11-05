# The QUEST
[Dokument - Zadanie projektu](https://docs.google.com/document/d/1cKQABYewh4Za8PkzfCHkz6zIMjVb64-OHdDwqiUYUQQ/edit?tab=t.0#heading=h.ihsraonxsqv0)

Projekt sa zaoberá predikovaním závislých hodnôt premennej **oximetry (predikovaná premenná)** pomocou metód strojového učenia.

#### Očakavaný výstup projektu:
1. najlepší model strojového učenia 
2. data pipeline pre jeho vybudovanie na základe vstupných dát

### Authors
- Johanna Tilešová [@JohannaTilesova](https://github.com/johannatilesova)
- Adam Pečenka [@AdamPecenka](https://github.com/AdamPecenka)

## 1. fáza - prieskumná analýza
### 1.1 Základný opis dát spolu s ich charakteristikami
#### EDA s vizualizáciou
- [x] Analýza štruktúr dát ako súbory (štruktúry a vzťahy, počet, typy, …), záznamy (štruktúry, počet záznamov, počet atribútov, typy, …)
- [x] Analýza jednotlivých atribútov: pre zvolené významné atribúty (min 10) analyzujte ich distribúcie a základné deskriptívne štatistiky a či spĺňa predpísané podmienky a rozsah meraných hodnôt. 
- [x] Párová analýza dát: Identifikujte vzťahy a závislostí medzi dvojicami atribútov.
- [x] Párová analýza dát: Identifikujte závislosti medzi predikovanou premennou a ostatnými premennými (potenciálnymi prediktormi).
- [x] Dokumentujte Vaše prvotné zamyslenie k riešeniu zadania projektu, napr. sú niektoré atribúty medzi sebou závislé? od ktorých atribútov závisí predikovaná premenná? či je potrebné kombinovať záznamy z viacerých súborov? 

### 1.2 Identifikácia problémov, integrácia a čistenie dát
- [x] Identifikujte aj prvotne riešte problémy v dátach napr.: nevhodná štruktúra dát, duplicitné záznamy, ktoré môžu vznikať po určitých dátových transformáciach, nejednotné formáty, chýbajúce hodnoty, vychýlené hodnoty. V dátach sa môžu nachádzať aj iné, tu nevymenované problémy, resp. menej problémov ako bolo uvedených.
- [x] Kontrola správnosť v dátach 
  - či obsahujú abnormálne hodnoty 
  - či obsahujú nelogické dátové vzťahy, ktoré sú následkom dátovej kolekcie a anotovania dát
- [x] Vychýlené hodnoty (outlier detection), vyskúšajte riešiť problém min. 2 technikami 
  - odstránenie vychýlených alebo odľahlých pozorovaní 
  - nahradenie vychýlenej hodnoty hraničnými hodnotami rozdelenia (napr. 5%, 95%)

### 1.3 Formulácia a štatistické overenie hypotéz o dátach
- [x] Sformulujte dve hypotézy o dátach v kontexte zadanej predikčnej úlohy. Formulované hypotézy overte vhodne zvolenými štatistickými testami.
  - _(SK) FiO₂ má v priemere vyššiu hodnotu v stave s oximetry ako bez nej._
  - _(EN) FiO₂ has, on average, a higher value in the state with oximetry than without it._
- [x] Overte či Vaše štatistické testy majú dostatok podpory z dát, teda či majú dostatočne silnú štatistickú silu.

## 2. fáza - Predspracovanie údajov 
Výsledkom má byt dátová sada (csv alebo tsv), kde jedno pozorovanie je opísané jedným riadkom.
- **scikit-learn** vie len numerické dáta, takže niečo treba spraviť s nenumerickými dátami. 
- replikovateľnosť predspracovania na trénovacej a testovacej množine dát, aby ste mohli zopakovať predspracovanie viackrát podľa Vašej potreby (iteratívne).

### 2.1 Realizácia predspracovania dát (5b). 
- [ ] Dáta si rozdeľte na trénovaciu a testovaciu množinu podľa vami preddefinovaného pomeru. Ďalej pracujte len s trénovacím datasetom.
- [ ] Transformujte dáta na vhodný formát pre strojové učenie t.j. jedno pozorovanie musí byť opísané jedným riadkom a každý atribút musí byť v numerickom formáte. Iteratívne integrujte aj kroky v predspracovaní dát z prvej fázy ako celok. 
- [ ] Transformujte atribúty dát pre strojové učenie podľa dostupných techník minimálne: scaling (2 techniky), transformers (2 techniky) a ďalšie. Cieľom je aby ste testovali efekty a vhodne kombinovali v dátovom pipeline (od časti 2.3 a v 3. fáze). 
- [ ] Zdôvodnite Vaše voľby/rozhodnutie pre realizáciu (t.j. zdokumentovanie)

### 2.2 Výber atribútov pre strojové učenie (5b)
- [ ] Zistite, ktoré atribúty (features) vo vašich dátach pre ML sú informatívne k predikovanej premennej (minimálne 3 techniky s porovnaním medzi sebou). 
- [ ] Zoraďte zistené atribúty v poradí podľa dôležitosti. 		
- [ ] Zdôvodnite Vaše voľby/rozhodnutie pre realizáciu (t.j. zdokumentovanie)

### 2.3 Replikovateľnosť predspracovania (5b)
- [ ] Upravte váš kód realizujúci predspracovanie trénovacej množiny tak, aby ho bolo možné bez ďalších úprav znovu použiť na predspracovanie testovacej množiny v kontexte strojového učenia.
- [ ] Využite možnosti sklearn.pipeline

## 3. fáza - Strojové učenie
