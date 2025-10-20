# 1.1 Základný opis dát spolu s ich charakteristikami
- `isnull()` pre všetky tabuľky - počet null hodnôt v každom stĺpci
- spraviť funkciu na top10 atribútov

### Top 10 atribútov
| Atribút               | Co to znamená                                  |
|-----------------------|------------------------------------------------|
| PI (Perfusion Index)  | perfúzia / kvalita signálu                     |
| Motion/Activity index | artefakty z pohybu                             |
| Signal Quality Index  | kvalita merania                                |
| Skin Temperature      | periférna perfúzia ovplyvňuje PPG              |
| EtCO₂                 | stabilita dýchania                             |
| RR                    | respiračná stabilita                           |
| PRV                   | autonómny stav                                 |
| BP                    | perfúzia                                       |
| CO                    | celkové okysličenie systému                    |
| FiO₂                  | nie priamy, ale prostredníctvom stavu pacienta |

# 1.2 Identifikácia problémov, integrácia a čistenie dát

- zistit co je `ssn` v tabulke pacient
- pozriet sa na `residence` v tabulke pacient - preco tam je tolko NaN

## Prvotne problémy v dátach
#### Nevhodná štruktúra dát
- `current_location` v tabulke pacient - rozdelit na dva stlpce

#### Duplicitné záznamy
- pozriet pacienta (user)

#### Nejednotné formáty
- `revision` v tabulke station
- `registration` v tabulke pacient
- mozno zobrat do uvahy aj stpce s indexom napr. SpO₂ lebo ten dolny index hadze ako chybu ?

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
