# Reva Voss - LoRA Training Guide

## Co je LoRA a preco ho potrebujeme

LoRA (Low-Rank Adaptation) je technika na dotrénovanie AI modelu na specificky vizual -
v nasom pripade na tvar Revy. Po natrenovaní LoRA budeme moct generovat konzistentne
fotky s rovnakou tvarou, telesnym typom a crtami.

---

## Krok 1: Pripravit "seed" obrazky

### Generovanie zakladnych referencnych fotiek

Pred trenovanim LoRA potrebujeme 15-30 kvalitnych referencnych obrazkov nasej postavy.

**Postup:**
1. Vygenerovat 100+ obrazkov pomocou character promptu z `PROMPTS_SFW.md`
2. Vybrat 15-30 najlepsich, kde je tvar konzistentna
3. Alternativne: pouzit PuLID/IP-Adapter na "uzamknutie" tvare z jedneho seed obrazku

### Poziadavky na training dataset:
- **Pocet**: 15-30 obrazkov (idealne 20-25)
- **Rozlisenie**: Minimalne 512x512, idealne 768x1024
- **Roznorodost**:
  - 5x close-up tvar (rozne uhly - front, 3/4, profil)
  - 5x half body (rozne oblecenie)
  - 5x full body (rozne pozy)
  - 5x rozne osvetlenie (denne, umele, outdoor, indoor)
  - Zvysok: mix
- **Pozadie**: Roznorodé (nie vzdy rovnake)
- **Oblecenie**: Roznorodé (aby sa LoRA naucilo tvar, nie outfit)

### Captioning (popisky):
Kazdy obrazok potrebuje textovy popis. Pouzit:
- **BLIP-2** alebo **WD Tagger** na automaticke captioning
- Manualne upravit - pridat trigger word

---

## Krok 2: Nastavenie trenovania

### Odporucany software:
| Nastroj | Pouzitie | Link |
|---------|----------|------|
| **Kohya_ss** | Najrozsirenejsi LoRA trainer | github.com/bmaltais/kohya_ss |
| **LoRA Easy Training Scripts** | Jednoduchsia alternativa | github.com/derrian-distro/LoRA_Easy_Training_Scripts |
| **ai-toolkit** | Moderny, podporuje FLUX | github.com/ostris/ai-toolkit |

### Parametre trenovania (SDXL):

```yaml
# Zakladne nastavenia
model_type: SDXL
network_type: LoRA
network_rank: 32          # dim (vyssie = viac detailov, ale pomalsi)
network_alpha: 16          # typicky rank/2
learning_rate: 0.0001      # 1e-4
unet_lr: 0.0001
text_encoder_lr: 0.00005   # 5e-5
optimizer: AdamW8bit
scheduler: cosine_with_restarts
batch_size: 1
resolution: 1024
epochs: 10-20
save_every_n_epochs: 2

# Trigger word
trigger_word: "reva_voss"
```

### Parametre trenovania (FLUX):

```yaml
# Pre FLUX modely
model_type: FLUX.1-dev  # alebo FLUX.2
network_type: LoRA
network_rank: 16-32
learning_rate: 4e-4
optimizer: Prodigy       # alebo AdamW
batch_size: 1-2
resolution: 1024
steps: 1500-3000
trigger_word: "reva_voss"
```

---

## Krok 3: Trenovanie

### Lokalne (ak mas GPU):
- **Minimum**: RTX 3060 12GB VRAM
- **Odporucane**: RTX 4070 Ti+ / 16GB+ VRAM
- **Cas**: 30-90 minut (zavisi od GPU a datasetu)

### Cloud (ak nemas GPU):
| Sluzba | Cena | VRAM |
|--------|------|------|
| RunPod | ~$0.40/hr | 24-48GB |
| Vast.ai | ~$0.30/hr | 24-48GB |
| Google Colab Pro | $10/mesiac | 15-40GB |
| CivitAI Training | Varies | Managed |

---

## Krok 4: Testovanie a iteracia

### Testovaci prompt:
```
reva_voss, a woman, portrait photo, looking at camera, natural lighting,
neutral background, photorealistic
```

### Co sledovat:
- [ ] Tvar je konzistentna
- [ ] Oci su spravna farba (hazel-green)
- [ ] Vlasy su spravna farba a dlzka
- [ ] Pihy su pritomne
- [ ] Nose piercing je viditelny
- [ ] Neni "overfit" (prilis rovnake pozy/pozadia)
- [ ] Neni "underfit" (tvar je nestabilna)

### LoRA strength:
- **0.6-0.7**: Jemnejsia podoba (viac variability)
- **0.7-0.85**: Optimalne (dobra podoba + flexibility)
- **0.85-1.0**: Velmi silna podoba (riziko overfit, menej flexibility)

**Odporucane**: `<lora:reva_voss:0.75>`

---

## Krok 5: Pouzitie v produkcii

### V prompte:
```
reva_voss, [zvysok promptu], <lora:reva_voss:0.75>
```

### Kombinacia s inymi technikami:
- **LoRA + IP-Adapter**: Este silnejsia konzistencia
- **LoRA + PuLID**: Pre doladenie tvare
- **LoRA + ControlNet**: Pre specificke pozy

---

## Alternativa: Bez LoRA (rychlejsie ale menej konzistentne)

Ak nechces trenovat LoRA, mozes pouzit:

### PuLID + FLUX Kontext
1. Vygeneruj jednu "seed" fotku Revy
2. Pouzi PuLID na kazdu dalsiu generaciu s referenciou na seed
3. Vyhoda: Ziadne trenovanie
4. Nevyhoda: Menej konzistentne ako LoRA

### IP-Adapter Face
1. Rovnaky princip - referencna fotka
2. IP-Adapter FaceID prenasa facial features
3. Moze sa kombinovat s LoRA

### FLUX Kontext (Character Reference)
1. FLUX.2 podporuje character reference nativne
2. Uploadnes referencnu fotku a model sa pokusi zachovat tvar
3. Funguje aj bez trenovania

---

## Doporuceny Workflow

```
1. Vygeneruj 100+ fotiek s character promptom (SDXL/FLUX)
     ↓
2. Vyber 20-25 najlepsich (konzistentna tvar)
     ↓
3. Captioning (BLIP-2 + manualna uprava)
     ↓
4. Trenuj LoRA (Kohya_ss / ai-toolkit)
     ↓
5. Testuj na roznych promptoch
     ↓
6. Iteruj (uprav dataset/parametre ak treba)
     ↓
7. Produkcia - generuj content s LoRA
```
