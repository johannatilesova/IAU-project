# 1. Základný opis dát spolu s ich charakteristikami
- `isnull()` pre všetky tabuľky - počet null hodnôt v každom stĺpci
### Atributy s priamym vplyvom:
| Atribút                                | Prečo ovplyvňuje SpO₂ (oximetriu)                                                            |
| -------------------------------------- | -------------------------------------------------------------------------------------------- |
| **FiO₂** (Fraction of inspired oxygen) | Najsilnejší prediktor – ak pacient dýcha vyššiu frakciu kyslíka, saturácia rastie            |
| **RR** (Respiratory rate)              | Rýchlosť dýchania priamo ovplyvňuje výmenu plynov v pľúcach                                  |
| **EtCO₂** (End-tidal CO₂)              | Je nepriamym ukazovateľom ventilácie – zlá ventilácia = CO₂ stúpa = klesá SpO₂               |
| **Hb level** (hemoglobín)              | Saturácia je % obsadenia hemoglobínu → ak je hemoglobínu málo, prenášaný kyslík je nižší     |
| **CO** (Cardiac output)                | Ovplyvňuje dodanie kyslíka do tkanív → nízky CO = zlé okysličenie                            |
| **BP** (systolický/diastolický)        | Slabý perfúzny tlak = menej kyslíka v periférnych tkanivách                                  |
| **PRV** / HR (heart rate)              | Hypoxia typicky mení srdcovú činnosť, taktiež PRV súvisí s autonómnou reguláciou okysličenia |

### Atributy so sekundárnym vplyvom:
| Atribút                           | Prečo môže súvisieť                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------ |
| **PI** (Perfusion index)          | Ak je perfúzia slabá → môže byť nepresný odhad SpO₂ alebo reálne znížené okysličenie |
| **Skin temperature**              | Termoregulácia odhaľuje periférnu perfúziu, hypoxia znižuje teplotu periférií        |
| **PVI** (Pleth Variability Index) | Odrazuje objemové zmeny počas dychu → môže identifikovať dýchacie nepravidelnosti    |
| **Motion / activity index**       | Pohyb artefakty môžu krátkodobo meniť čítanie a presnosť snímky                      |
| **Signal quality index**          | Pri nízkej kvalite signálu môžu byť SpO₂ hodnoty nepresné                            |

# 1.2 Identifikácia problémov, integrácia a čistenie dát

- zistit co je `ssn` v tabulke pacient
- pozriet sa na `residence` v tabulke pacient - preco tam je tolko NaN

### Prvotne problémy v dátach
#### Nevhodná štruktúra dát
- `current_location` v tabulke pacient - rozdelit na dva stlpce

#### Duplicitné záznamy
- pozriet pacienta (user)

#### Nejednotné formáty
- `revision` v tabulke station
- `registration` v tabulke pacient

#### Chybajcúce a vychylené hodnoty
- vychylene hodnoty zistime z EDA (asi cez boxploty)

### Kontrola správnosti v dátach
