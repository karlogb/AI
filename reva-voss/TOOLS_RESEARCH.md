# AI Influencer - Nastroje & Technologie Research

> Posledna aktualizacia: Marec 2026

---

## 1. Generovanie Obrazkov (Image Generation)

### 1.1 Modely / Checkpointy

| Model | Typ | SFW | NSFW | Poznamka |
|-------|-----|-----|------|----------|
| **Stable Diffusion XL (SDXL)** | Open-source | Ano | S NSFW checkpointom | Zaklad, siroky ekosystem |
| **Stable Diffusion 3.5** | Open-source | Ano | Limitovane | Lepsie text rendering |
| **FLUX.1 Dev** | Open-source | Ano | S unlockom | Vynikajuca kvalita, BFL |
| **FLUX.2** | Open-source | Ano | S unlockom | Najnovsi, este lepsia kvalita |
| **FLUX Kontext** | Open-source | Ano | Ano | Character reference nativne |
| **Midjourney V7** | Cloud/SaaS | Ano | Nie | Najlepsie pre rychle prototypovanie |
| **RealVisXL V5** | SDXL checkpoint | Ano | NSFW variant | Top pre fotorealizmus |
| **Juggernaut XL** | SDXL checkpoint | Ano | NSFW variant | Versatilny, kvalitny |
| **epiCRealism** | SDXL checkpoint | Ano | NSFW variant | Vynikajuce portréty |
| **CyberRealistic Pony** | Pony checkpoint | Ano | Ano | Dobry pre NSFW |

### 1.2 UI / Rozhrania

| Nastroj | Typ | Vyhody | Nevyhody |
|---------|-----|--------|----------|
| **ComfyUI** | Node-based | Najflexibilnejsi, workflows, produkcia | Strmsia learning curve |
| **Automatic1111 WebUI** | Web UI | Jednoduchy, siroky ekosystem | Pomalsi vyvoj |
| **Forge WebUI** | Web UI (fork A1111) | Rychlejsi, menej RAM | Menej extensions |
| **Fooocus** | Zjednoduseny UI | Najjednoduchsi, Midjourney-like | Menej kontroly |

**Odporucanie**: **ComfyUI** pre produkciu (workflows sa daju automatizovat),
**Fooocus** pre rychle testovanie.

### 1.3 Face Consistency Nastroje

| Nastroj | Pouzitie | Kvalita |
|---------|----------|---------|
| **PuLID (Pure Identity)** | Zero-shot face identity | Velmi dobra, nativna podpora vo FLUX |
| **PuLID Flux II** | Najnovsia verzia pre FLUX.2 | Excelentna |
| **IP-Adapter FaceID** | Face reference z obrazku | Dobra |
| **InstantID** | Instant face identity transfer | Velmi dobra |
| **ReActor** | Face swap post-processing | Dobra pre post-processing |
| **FLUX Kontext** | Native character reference | Excelentna (built-in) |
| **LoRA** | Natrénovany model na tvar | Najlepsia konzistencia |

**Odporucanie**: **LoRA** (najlepsia konzistencia) + **PuLID** (ako backup/reinforcement).
Vid `LORA_TRAINING_GUIDE.md` pre detaily.

---

## 2. Generovanie Videa (Video Generation)

### 2.1 Cloud / SaaS Video Generatory

| Nastroj | Cena | Kvalita | Dlzka | NSFW |
|---------|------|---------|-------|------|
| **Kling AI 2.0** | Freemium / $8+/mo | Excelentna | 5-10s | Nie |
| **Runway Gen-4** | $15+/mo | Velmi dobra | 4-16s | Nie |
| **Pika 2.0** | Freemium | Dobra | 3-5s | Nie |
| **Hailuo AI (MiniMax)** | Freemium | Velmi dobra | 5-6s | Nie |
| **Luma Dream Machine** | Freemium | Dobra | 4-5s | Nie |
| **Vidu** | Freemium | Dobra | 4-8s | Nie |

### 2.2 Lokalne Video Generatory

| Nastroj | Pouzitie | HW poziadavky |
|---------|----------|---------------|
| **AnimateDiff** | SD-based animacia | 12GB+ VRAM |
| **CogVideoX** | Open-source text2video | 24GB+ VRAM |
| **Wan2.1** | Open-source, kvalitne | 24GB+ VRAM |
| **Hunyuan Video** | Tencent, open-source | 24GB+ VRAM |

### 2.3 Talking Head / Lip Sync

| Nastroj | Pouzitie | Cena |
|---------|----------|------|
| **Hedra** | Fotka + audio = hovoriaci clovek | Freemium |
| **D-ID** | Talking avatar | $6+/mo |
| **HeyGen** | Profesionalny avatar | $29+/mo |
| **SadTalker** | Open-source lip sync | Free (lokalne) |
| **Wav2Lip** | Open-source lip sync | Free (lokalne) |
| **MuseTalk** | Real-time lip sync | Free (lokalne) |

**Odporucanie pre TikTok**: **Kling AI** alebo **Runway** pre kratke moto klipy,
**Hedra** pre "talking to camera" content.

---

## 3. AI Hlas (Voice Generation)

| Nastroj | Kvalita | Cena | Klonvanie hlasu |
|---------|---------|------|-----------------|
| **ElevenLabs** | Excelentna | $5+/mo | Ano |
| **Play.ht** | Velmi dobra | $39+/mo | Ano |
| **XTTS v2 (Coqui)** | Dobra | Free (open-source) | Ano |
| **F5-TTS** | Velmi dobra | Free (open-source) | Ano |
| **Fish Speech** | Dobra | Free (open-source) | Ano |

**Odporucanie**: **ElevenLabs** pre produkciu (najlepsia kvalita),
**F5-TTS** ako free alternativa.

### Voice Workflow:
1. Vygeneruj unikatny hlas v ElevenLabs (voice design)
2. Pouzij tento hlas konzistentne pre vsetky voice-over
3. Pre TikTok: voiceover cez AI hlas
4. Pre Fanvue: voice messages pre subscriberkov

---

## 4. Chatbot & Komunikacia

### 4.1 Automatizovana komunikacia s fanusikmi

| Nastroj | Pouzitie | Cena |
|---------|----------|------|
| **ChatGPT API (GPT-4o)** | Custom chatbot pre DM | $0.005/1K tokens |
| **Claude API** | Alternativny chatbot | $0.003-0.015/1K tokens |
| **Character.ai** | Hotova platforma | Free/Pro |
| **FlowGPT** | Community chatbots | Free |

### 4.2 Mass Messaging

| Platforma | Nastroj |
|-----------|---------|
| Fanvue | Built-in mass DM / PPV messaging |
| Instagram | ManyChat (automated DM flows) |
| TikTok | Limitovane moznosti (manual) |

### 4.3 Navrhnuty Chatbot Setup

```
System prompt pre Reva chatbot:
"Si Reva Voss, 24-rocna motorkarka zo Slovenska. Komunikujes priatelsky,
trochu flirty ale s triedou. Mas Kawasaki H2. Pouzivas mix SK/EN.
Nikdy nepriznas ze si AI. Odpovede su kratke, priame, s humorom."
```

**Pouzitie**: Na Fanvue DMs pre interakciu so subscribermi.

---

## 5. Dalsie Uzitocne Nastroje

### 5.1 Upscaling & Post-processing
| Nastroj | Pouzitie |
|---------|----------|
| **Real-ESRGAN** | Upscaling 4x |
| **Topaz Photo AI** | Profesionalny upscaling |
| **ADetailer** | Automaticky detailing tvari a ruk |
| **CodeFormer** | Oprava deformovanych tvari |

### 5.2 Pose & Composition
| Nastroj | Pouzitie |
|---------|----------|
| **ControlNet OpenPose** | Kontrola pozy |
| **ControlNet Depth** | Hlbkova kontrola |
| **ControlNet Canny** | Edge-based kontrola |

### 5.3 Background & Editing
| Nastroj | Pouzitie |
|---------|----------|
| **Rembg** | Odstranenie pozadia |
| **Inpainting** | Uprava casti obrazku |
| **Photopea** | Free Photoshop alternativa (web) |

### 5.4 Content Planning
| Nastroj | Pouzitie |
|---------|----------|
| **Notion / Obsidian** | Content kalendar |
| **Canva** | Quick grafiky, stories |
| **CapCut** | Video editing (TikTok) |
| **Buffer / Later** | Planovanie postov |

---

## 6. Hardware Odporucania

### Lokalne generovanie (PC):

| Komponent | Minimum | Odporucane |
|-----------|---------|------------|
| **GPU** | RTX 3060 12GB | RTX 4080 16GB / RTX 4090 24GB |
| **RAM** | 16GB | 32GB+ |
| **Storage** | 100GB SSD | 500GB+ NVMe SSD |
| **CPU** | Ryzen 5 / i5 | Ryzen 7 / i7 |

### Cloud alternativy:
| Sluzba | Cena/hodina | GPU |
|--------|-------------|-----|
| **RunPod** | $0.40-1.00 | A100/H100 |
| **Vast.ai** | $0.30-0.80 | Rozne |
| **Google Colab Pro** | $10/mesiac | T4/A100 |
| **CivitAI** | Credits | Managed |
| **RunComfy** | Credits | Managed ComfyUI |

---

## 7. Naklady - Mesacny odhad

| Polozka | Cena/mesiac |
|---------|-------------|
| Midjourney (Standard) | $30 |
| ElevenLabs (Starter) | $5 |
| RunPod (10hrs/mesiac) | ~$5-10 |
| Kling AI (Pro) | ~$8 |
| Hedra (Basic) | ~$10 |
| Fanvue (platforma) | 20% z prijimu |
| **TOTAL (bez HW)** | **~$60-80/mesiac** |

Alternativne s vlastnym GPU: iba ElevenLabs + Kling = ~$13/mesiac + elektrinu.

---

## 8. Odporucany Stack pre Reva Voss

### Tier 1 (Budget - ~$15/mesiac):
- **Obrazky**: ComfyUI lokalne (FLUX.2 + PuLID) alebo Fooocus
- **Video**: Kling AI free tier + CapCut edit
- **Hlas**: F5-TTS (free) alebo ElevenLabs $5
- **Chatbot**: Claude/GPT API (minimal usage)

### Tier 2 (Stredny - ~$60/mesiac):
- **Obrazky**: ComfyUI + LoRA + Midjourney pre prototypy
- **Video**: Kling AI Pro + Hedra
- **Hlas**: ElevenLabs Starter
- **Chatbot**: GPT-4o API

### Tier 3 (Profesionalny - ~$150+/mesiac):
- **Obrazky**: ComfyUI produkcia + RunPod cloud + Midjourney
- **Video**: Runway Pro + Kling Pro + HeyGen
- **Hlas**: ElevenLabs Pro
- **Chatbot**: Custom chatbot s GPT-4o
- **Planovanie**: Buffer + Notion
