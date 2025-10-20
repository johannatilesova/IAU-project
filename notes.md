# 1.1 Základný opis dát spolu s ich charakteristikami
- `isnull()` pre všetky tabuľky - počet null hodnôt v každom stĺpci
- spraviť funkciu na top10 atribútov
- v grafoch parovej analyzi farebne rozlisit a pridat legendu pre jednotlive boxploty
- doplnit grafy distribucii (aspon pre nasich 10 atributov)

### Top 10 atribútov
| Atribút               | Co to znamená                                  |
|-----------------------|------------------------------------------------|
| Motion/Activity index | artefakty z pohybu                             |
| EtCO₂                 | stabilita dýchania                             |
| PRV                   | autonómny stav                                 |
| BP                    | perfúzia                                       |
| PI (Perfusion Index)  | perfúzia / kvalita signálu                     |
| Skin Temperature      | periférna perfúzia ovplyvňuje PPG              |
| CO                    | celkové okysličenie systému                    |
| Signal Quality Index  | kvalita merania                                |
| RR                    | respiračná stabilita                           |
| FiO₂                  | nie priamy, ale prostredníctvom stavu pacienta |

# 1.2 Identifikácia problémov, integrácia a čistenie dát

#### Nejednotné formáty
- mozno zobrat do uvahy aj stpce s indexom napr. SpO₂ lebo ten dolny index nazvu stlpca hadze ako chybu ?

#### Chybajcúce a vychylené hodnoty
- vychylene hodnoty zistime z EDA (asi cez boxploty)
- pri `Motion/Activity index` nie je v meta-dátach uvedený rozsah (`Value Range = NaN`)

### Kontrola správnosti v dátach
- Abnormálne hodnoty sú fyziologicky nemožné – napríklad SpO₂ nad 100 %, srdcová frekvencia 800 bpm alebo teplota 0°C
- Nelogické dátové vzťahy sú také, kde jednotlivé čísla vyzerajú normálne, ale spolu nedávajú medicínsky zmysel – napríklad vysoká FiO₂ a zároveň extrémne nízka SpO₂

### Vychýlené hodnoty
Outlier = hodnota, ktorá je extrémne odlišná od ostatných.

1. Odstránenie vychýlených alebo odľahlých pozorovaní 
   - chyba merania, hodnota je fyziologicky nemožná
2. Nahradenie vychýlenej hodnoty hraničnými hodnotami rozdelenia (napr. 5%, 95%)
   - „extrémne hodnoty zrežem na rozumné limity“ 
   - Napr. nastavíš:
     - všetko pod 5. percentil → na hodnotu 5. percentilu 
     - všetko nad 95. percentil → na hodnotu 95. percentilu
