# CLAUDE.md - Project Instructions

## Projekt
Toto je projekt **Reva Voss** - AI-generovaná virtuálna influencerka (motorkárka / automotive lifestyle). Cieľom je vytvoriť konzistentný, realistický AI-generovaný obsah pre sociálne siete a premium platformy.

## Jazyk
- Komunikácia s používateľom: **slovenčina**
- Súbory a dokumentácia: slovenčina aj angličtina (prompty v angličtine, popisy v slovenčine)
- Commit messages: angličtina
- PR descriptions: slovenčina + angličtina mix

## Pravidlá pre commity a PR
- Každý commit musí mať jasný, popisný message
- Každý Pull Request MUSÍ mať poriadny title + description s:
  - Čo sa robilo a prečo
  - Zoznam konkrétnych zmien
  - Prípadné TODO do budúcnosti
- README.md changelog sa aktualizuje pri každej väčšej zmene
- Branch naming: `claude/<popis>-<session-id>`

## Štruktúra projektu
```
AI/
├── CLAUDE.md                 # Tieto inštrukcie (čítaj vždy prvé!)
├── README.md                 # Popis projektu + changelog
├── CHARACTER_BIBLE.md        # Vzhľad, osobnosť, backstory
├── CONTENT_STRATEGY.md       # Stratégia obsahu pre platformy
├── LORA_TRAINING_GUIDE.md    # Technický návod LoRA tréning
├── PROMPTS_SFW.md            # SFW prompty pre generovanie
├── PROMPTS_NSFW.md           # NSFW prompty (Fanvue exclusive)
├── PROMPTS_VEHICLES.md       # Prompty pre vozidlá
├── MONETIZATION.md           # Monetizačná stratégia a revenue plány
├── POSTING_CALENDAR.md       # Týždenný/mesačný posting kalendár
├── CAPTIONS_TEMPLATES.md     # Caption šablóny a hashtagy
├── REVA_VOICE.md             # Komunikačný profil - ako Reva hovorí/píše
├── TROUBLESHOOTING.md        # Riešenie problémov pri generovaní
├── BRAND_PARTNERSHIPS.md     # Stratégia spolupráce s brandmi
├── TOOLS_RESEARCH.md         # Prehľad AI nástrojov
├── .claude/
│   ├── memory.md             # Trvalá pamäť - fakty o projekte
│   ├── decisions.md          # Log rozhodnutí a prečo
│   └── style-guide.md       # Štýlový sprievodca pre konzistentnosť
└── reference-photos/
    ├── motorcycle/           # Kawasaki Ninja H2 referenčné fotky
    ├── car/                  # BMW M5 F90 referenčné fotky
    ├── helmet/               # Helma referenčné (TODO)
    ├── outfits/              # Outfity referenčné (TODO)
    └── environments/         # Prostredia referenčné (TODO)
```

## Kľúčové pravidlá

### Postava - Reva Voss
- 24 rokov, atletická postava, tmavé vlnité vlasy po ramená
- Hazel-zelené oči, svetlá olivová pleť, pehy cez nos
- Malý polmesiac tetovanie za ľavým uchom
- Strieborný nose stud na ľavej nosnej dierke
- NIKDY nemeniť fyzické atribúty!

### Vozidlá
| Vozidlo | ŠPZ (SK) | Kľúčový look |
|---------|----------|--------------|
| Kawasaki Ninja H2 (2015) | BT-KWSH2 | Mirror black chrome, zelený rám, Akrapovič |
| BMW M5 F90 (2019) | XX-BMWM5 | Matná čierna fólia, žlté angel eyes, Remus |

### ŠPZ pravidlá (KRITICKÉ!)
- ŠPZ sa NIKDY nezobrazujú čitateľne na fotkách
- Povolené: rozmazané, v tieni, orezané, príliš ďaleko
- EU modrý prúžok so SK môže byť viditeľný
- V negatívnom prompte vždy: `(readable text on license plate:1.5)`

### Helma
- AGV Pista GP RR, matná čierna s červenými akcentmi

### Telefón
- iPhone 15 Pro Max, Natural Titanium, priehľadný case

### Prostredia
- Garáž: industriálna, betón, tehla, neon červené svetlo
- Spálňa: minimalistická, sivá/biela, LED pásy, monstera
- Kúpeľňa: biela + drevené akcenty
- Outdoor: slovenské hory, Bratislava staré mesto

## Workflow
1. Pred každou prácou prečítaj CLAUDE.md + .claude/memory.md
2. Kontroluj decisions.md pre predchádzajúce rozhodnutia
3. Dodržiavaj style-guide.md pre konzistentnosť
4. Aktualizuj memory.md ak sa dozvieš niečo nové
5. Zaznamenaj dôležité rozhodnutia do decisions.md
6. Aktualizuj README.md changelog
7. Commitni a pushni s poriadnym popisom
