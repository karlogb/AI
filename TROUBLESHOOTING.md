# Troubleshooting - Riešenie problémov

> Časté problémy pri AI generovaní obsahu a ich riešenia.
> Aktualizuj pri každom novom probléme a riešení.

---

## Tvár a konzistentnosť

### Problém: Tvár sa mení medzi generáciami
**Príčina:** Nedostatočný LoRA weight alebo chýbajúce face reference
**Riešenie:**
- Použiť "triple stack": LoRA (weight 0.6-0.7) + PuLID (0.8) + ControlNet OpenPose
- Vždy zahrnúť detailný popis tváre v prompte
- Reference image cez IP-Adapter FaceID
- Seed locking pre podobné výsledky

### Problém: Oči majú zlú farbu
**Príčina:** Model defaultuje na hnedé/modré oči
**Riešenie:**
- Explicitne v prompte: `hazel-green eyes, green-hazel iris`
- V negatívnom prompte: `blue eyes, brown eyes, dark eyes`
- Zvýšiť weight: `(hazel-green eyes:1.3)`

### Problém: Vlasy sú príliš dlhé/krátke/rovné
**Príčina:** Vágny popis vlasov
**Riešenie:**
- Presný popis: `dark brunette wavy hair, shoulder-length, natural waves`
- Negatívny: `straight hair, curly hair, long hair, short hair, blonde`
- Weight: `(shoulder-length dark wavy hair:1.2)`

### Problém: Pehy nie sú viditeľné
**Príčina:** Model ich ignoruje pri nižšom rozlíšení
**Riešenie:**
- `(light freckles across nose and cheeks:1.2)`
- Generovať vo vyššom rozlíšení (min 1024x1024)
- ADetailer pre face refinement

---

## Ruky a anatómia

### Problém: Deformované ruky / extra prsty
**Príčina:** Klasický SD problém, hlavne pri komplexných pózach
**Riešenie:**
- Negatívny prompt: `bad hands, extra fingers, missing fingers, fused fingers, deformed hands, mutated hands`
- ControlNet OpenPose pre správnu pózu
- ADetailer s "hand" detection
- Generovať viac variant a vybrať najlepšiu
- Inpainting na opravu rúk

### Problém: Anatómia je "off" (proporcie)
**Príčina:** Nesprávny aspect ratio alebo komplexná póza
**Riešenie:**
- ControlNet OpenPose alebo DWPose
- Referenčná póza z reálnej fotky
- `(correct human anatomy:1.2)` v prompte
- Vyhnúť sa extrémnym uhlom kamery

---

## Vozidlá

### Problém: Motorka nevyzerá ako Ninja H2
**Príčina:** Model nepozná špecifický model
**Riešenie:**
- Detailný popis: `Kawasaki Ninja H2, mirror black chrome fairings, green trellis frame, supercharger badge visible, Akrapovic carbon exhaust`
- IP-Adapter s referenčnou fotkou motorky
- ControlNet Canny/Depth z referenčnej fotky
- LoRA trénovaný na H2 fotkách (ak dostupný)

### Problém: BMW M5 má zlé detaily
**Príčina:** Model mixuje rôzne generácie M5
**Riešenie:**
- Špecifikovať: `BMW M5 F90 2019, matte black wrap, yellow angel eye headlights, black wheels, blue M brake calipers`
- Referenčné fotky cez IP-Adapter
- ControlNet pre správny tvar

### Problém: ŠPZ je čitateľná!
**Príčina:** Model generuje realistický text na ŠPZ
**Riešenie (KRITICKÉ):**
- VŽDY v negatívnom prompte: `(readable text on license plate:1.5), (visible license plate text:1.3), (clear license plate:1.3)`
- Kompozícia: ŠPZ mimo záber, v tieni, rozmazaná
- Post-processing: Blur ŠPZ v editore
- Inpainting: Prepísať ŠPZ oblasť
- Motion blur efekt na celé vozidlo

---

## Osvetlenie a farby

### Problém: Flat, nudné osvetlenie
**Príčina:** Chýba špecifický lighting prompt
**Riešenie:**
- Vždy špecifikovať svetlo: `dramatic side lighting, neon red glow, golden hour sunlight, moody low-key lighting`
- Pridať zdroj svetla: `lit by neon signs, single overhead light, window light`
- Negatívny: `flat lighting, overexposed, evenly lit`

### Problém: Farby sú príliš saturované / nerealistické
**Príčina:** Model "AI look"
**Riešenie:**
- `raw photo, film grain, natural colors, muted tones`
- Znížiť CFG scale (7-8 namiesto 10+)
- Post-processing: desaturate mierne
- Negatívny: `oversaturated, HDR, hyperrealistic colors`

### Problém: Skin tone je nekonzistentný
**Príčina:** Rôzne lighting conditions
**Riešenie:**
- Vždy: `light olive skin tone, warm undertone, Mediterranean complexion`
- Negatívny: `pale skin, dark skin, tan, sunburn`
- Konzistentný lighting setup medzi setmi

---

## Kvalita a artefakty

### Problém: Rozmazané detaily / low quality output
**Príčina:** Nízke rozlíšenie alebo nedostatočné steps
**Riešenie:**
- Generovať min 1024x1024, upscale na 2048+
- Min 30 sampling steps (DPM++ 2M Karras)
- Hires fix s 0.5-0.7 denoise
- 4x-UltraSharp upscaler

### Problém: "AI look" - príliš perfect, plastový
**Príčina:** Prílišná kvalita bez imperfections
**Riešenie:**
- Pridať: `raw photo, film grain, slight imperfections, pores visible, natural skin texture`
- Znížiť CFG (7-9)
- Photorealistic checkpoint (RealVisXL, Juggernaut)
- Negatívny: `airbrushed, plastic skin, perfect skin, smooth skin`

### Problém: Watermark / text artefakty
**Príčina:** Training data contamination
**Riešenie:**
- Negatívny: `watermark, text, signature, logo, username, copyright`
- Čistý checkpoint bez NSFW merge issues

---

## Prostredia

### Problém: Garáž nevyzerá realisticky
**Príčina:** Vágny popis
**Riešenie:**
- Detailný prompt: `industrial garage interior, concrete floor with oil stains, exposed brick walls, tool wall with wrenches and sockets, red neon LED strip light, motorcycle hydraulic lift, dirty workbench`
- Referenčná fotka cez ControlNet Depth

### Problém: Outdoor scéna nevyzerá ako Slovensko
**Príčina:** Model nemá koncept slovenských ciest
**Riešenie:**
- `European mountain road, alpine scenery similar to Alps, coniferous forest, Tatra mountains, winding asphalt road, European road markings`
- Referenčné fotky slovenských ciest
- Post-processing: Color grade pre "European" look

---

## Workflow problémy

### Problém: Generovanie trvá príliš dlho
**Riešenie:**
- Batch generovanie: viac obrázkov naraz
- Nižší resolution pre drafty, upscale len finálne
- Cloud GPU (RunPod) ak lokálny HW nestíha
- Znížiť sampling steps pre testovacie generácie (15-20)

### Problém: VRAM out of memory
**Riešenie:**
- Znížiť batch size na 1
- Použiť --medvram alebo --lowvram flag
- FP16 precision
- Vypnúť nepotrebné extensions
- Zavrieť ostatné GPU aplikácie

### Problém: ControlNet nemá efekt
**Riešenie:**
- Skontrolovať preprocessor output (preview)
- Zvýšiť ControlNet weight (0.8-1.0)
- Správny model pre správny preprocessor (OpenPose pre pózy, Canny pre edges)
- Control mode: "Balanced" alebo "ControlNet is more important"

---

## Checklist pred publikovaním

- [ ] Tvár je konzistentná s CHARACTER_BIBLE
- [ ] Oči sú hazel-zelené
- [ ] Vlasy sú tmavé, vlnité, po ramená
- [ ] Pehy viditeľné (ak close-up)
- [ ] Nose stud na ľavej strane
- [ ] Ruky vyzerajú normálne (5 prstov na každej)
- [ ] ŠPZ NIE JE čitateľná
- [ ] Vozidlo zodpovedá popisu
- [ ] Osvetlenie je moody/dramatic
- [ ] Žiadne AI artefakty (watermark, text, deformácie)
- [ ] Správny aspect ratio pre platformu
- [ ] Žiadne NSFW na SFW platformách
