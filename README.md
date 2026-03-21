# AI - Reva Voss Project

## O projekte
AI-generovaná virtuálna influencerka **Reva Voss** (24 rokov) - motorkárka a automotive lifestyle tvorca obsahu. Projekt zahŕňa generovanie realistických AI fotografií pre sociálne siete (TikTok, Instagram) a premium obsah (Fanvue).

## Štruktúra projektu

```
AI/
├── README.md                 # Tento súbor
├── CHARACTER_BIBLE.md        # Kompletný popis postavy (vzhľad, štýl, osobnosť)
├── CONTENT_STRATEGY.md       # Obsahová stratégia pre sociálne siete
├── LORA_TRAINING_GUIDE.md    # Návod na tréning LoRA modelu pre konzistentný vzhľad
├── PROMPTS_SFW.md            # SFW prompty (lifestyle, moto, selfie, outdoor)
├── PROMPTS_NSFW.md           # NSFW prompty (Fanvue exclusive, tiers 1-3)
├── PROMPTS_VEHICLES.md       # Prompty pre vozidlá (solo, s postavou, detaily)
├── MONETIZATION.md           # Monetizačná stratégia a revenue plány
├── POSTING_CALENDAR.md       # Týždenný/mesačný posting kalendár
├── CAPTIONS_TEMPLATES.md     # Caption šablóny a hashtagy
├── REVA_VOICE.md             # Komunikačný profil (ako Reva hovorí/píše)
├── TROUBLESHOOTING.md        # Riešenie problémov pri generovaní
├── BRAND_PARTNERSHIPS.md     # Stratégia spolupráce s brandmi
├── TOOLS_RESEARCH.md         # Výskum AI nástrojov (Stable Diffusion, Flux, atď.)
├── CLAUDE.md                 # Inštrukcie pre Claude AI asistenta
├── .claude/                  # Claude memory a rozhodnutia
│   ├── memory.md             # Trvalá pamäť projektu
│   ├── decisions.md          # Log rozhodnutí
│   └── style-guide.md        # Štýlový sprievodca
└── reference-photos/         # Referenčné fotky pre tréning a štýl
    ├── motorcycle/           # Kawasaki Ninja H2 (19x .avif + 19x .png + INFO.md)
    ├── car/                  # BMW M5 F90 (34x .jpg + INFO.md)
    ├── helmet/               # AGV Pista GP RR (prázdne - TODO)
    ├── outfits/              # Oblečenie a štýl (prázdne - TODO)
    └── environments/         # Prostredia na fotky (prázdne - TODO)
```

## Vozidlá

| Vozidlo | Ročník | Kľúčové vlastnosti | ŠPZ (SK) |
|---------|--------|--------------------:|----------|
| **Kawasaki Ninja H2** | 2015 | First Edition #39/50, 200 HP supercharged, 76 km, Akrapovič, Brembo, Öhlins | BT-KWSH2 |
| **BMW M5 F90** | 2019 | 441 kW V8 xDrive, matná čierna fólia, Remus výfuk, žlté angel eyes | XX-BMWM5 |

> ŠPZ-ky sa na fotkách nikdy nezobrazujú čitateľne. Viditeľný môže byť len modrý EU prúžok so SK.

## Changelog

### 2026-03-20 - Založenie projektu
- Vytvorený CHARACTER_BIBLE.md - kompletný popis Reva Voss (vzhľad, osobnosť, zázemie, outfity)
- Vytvorený CONTENT_STRATEGY.md - plán obsahu pre TikTok/IG/Fanvue
- Vytvorený LORA_TRAINING_GUIDE.md - technický návod na tréning vlastného LoRA modelu
- Vytvorený PROMPTS_SFW.md - 10 SFW promptov (motorka, selfie, outdoor, café, fitness)
- Vytvorený PROMPTS_NSFW.md - 6 NSFW promptov v 3 tieroch + pricing stratégia Fanvue
- Vytvorený TOOLS_RESEARCH.md - prehľad AI generačných nástrojov a checkpointov
- Vytvorená štruktúra reference-photos/ pre referenčné obrázky

### 2026-03-20 - Referenčné fotky a vozidlá
- Nahraté referenčné fotky Kawasaki Ninja H2 (19 ks z Schneider Motorradzentrum DE)
- Nahraté referenčné fotky BMW M5 F90 (34 ks z Auto Exclusive Slovakia, Pezinok)
- Konverzia AVIF → PNG pre lepšiu kompatibilitu (motorcycle/)
- Vytvorené INFO.md súbory s technickými údajmi oboch vozidiel
- Vytvorený PROMPTS_VEHICLES.md - 25+ promptov pre obe vozidlá:
  - 5x solo Ninja H2 (garáž, hory, noc, detaily motor/kokpit)
  - 6x solo BMW M5 (štúdio, noc, highway, hory, detaily predok/zadok)
  - 6x Reva + Ninja H2 (garáž, urban, jazda, helma off, pumpa, oprava)
  - 6x Reva + BMW M5 (štúdio, kapota, šofér, vystupovanie, nočná jazda, kaviareň)
  - 2x obe vozidlá spolu (garážová kolekcia, ranné odchádzanie)
- Slovenské ŠPZ: BT-KWSH2 (motorka), XX-BMWM5 (auto) - pravidlá pre blur/skrytie

### 2026-03-21 - Claude konfigurácia a business dokumenty
- Vytvorený CLAUDE.md - hlavné inštrukcie pre Claude AI asistenta
- Vytvorený .claude/memory.md - trvalá pamäť (vozidlá, stav projektu, preferencie)
- Vytvorený .claude/decisions.md - log rozhodnutí s template
- Vytvorený .claude/style-guide.md - vizuálna identita, prompt templates, social formáty
- Vytvorený MONETIZATION.md - Fanvue tiers, revenue ciele, náklady, KPI
- Vytvorený POSTING_CALENDAR.md - týždenný plán, sezónny obsah, batching stratégia
- Vytvorený CAPTIONS_TEMPLATES.md - caption šablóny pre IG/TikTok/Fanvue/Reddit + hashtag databáza
- Vytvorený REVA_VOICE.md - komunikačný profil, slovník, reakcie, red lines
- Vytvorený TROUBLESHOOTING.md - riešenia pre tvár, ruky, vozidlá, ŠPZ, osvetlenie, kvalitu
- Vytvorený BRAND_PARTNERSHIPS.md - potenciálni partneri, pitch templates, partnership formáty
