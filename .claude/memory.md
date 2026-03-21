# Memory - Trvalá pamäť projektu

> Tento súbor obsahuje fakty, preferencie a informácie nazbierané počas práce.
> Aktualizuj ho pri každom novom zistení.

## Používateľ
- Komunikuje po slovensky
- Vlastní obe vozidlá (Kawasaki Ninja H2 + BMW M5)
- Chce vytvoriť AI influencerku v moto/automotive niši
- Preferuje stručnú, efektívnu komunikáciu
- Pushuje fotky priamo na main branch, Claude pracuje na feature branches

## Projekt - stav
- **Fáza:** Príprava podkladov (character bible, prompty, referenčné fotky)
- **Ďalšie kroky:** Tréning LoRA modelu, prvé generovanie obrázkov
- **Chýba:** Referenčné fotky helmy, outfitov, prostredí

## Vozidlá - detaily

### Kawasaki Ninja H2
- **First Edition #39 z 50** kusov prvej série do Nemecka
- Rok 2015, 76 km najazdených (prakticky nová)
- 998 ccm, 147 kW (200 HP), supercharged 4-valec
- Mirror black chrome lak, zelený trellis rám
- Akrapovič karbónový výfuk, Brembo brzdy, Öhlins steering damper
- Krátky držiak ŠPZ, miniblinky, Bursig centrálny stojan
- Predáva Schneider Motorradzentrum (Nemecko)
- ŠPZ: BT-KWSH2 (slovenský štvorcový formát)
- 19 referenčných fotiek (.avif + .png konverzia)

### BMW M5 F90
- Rok 2019, 90 336 km
- 4395 ccm V8, 441 kW, xDrive 4x4, 8-stupňový automat
- Matná čierna fólia, Remus výfukový systém
- Žlté angel eyes, čierne disky, modré M brzdové strmene
- Panoramatická strecha, head-up display, kožený interiér
- VIN: WBSJF01070G967982
- Predáva Auto Exclusive Slovakia, Pezinok
- ŠPZ: XX-BMWM5 (slovenský dlhý EU formát)
- 34 referenčných fotiek (.jpg)

## Technické poznámky
- AVIF fotky treba konvertovať na PNG pre lepšiu kompatibilitu (heif-convert)
- Niektoré AVIF sú príliš veľké na priame čítanie (>256KB)
- JPG fotky BMW sú v poriadku na priame zobrazenie (~100-230KB)

## Preferované nástroje a modely (z TOOLS_RESEARCH.md)
- Stable Diffusion XL + LoRA pre konzistentnosť
- RealVisXL / Juggernaut XL ako base checkpointy
- Flux pre najvyššiu kvalitu (ak dostupný)
