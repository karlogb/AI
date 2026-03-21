# AI - Reva Voss Project

## About the Project
AI-generated virtual influencer **Reva Voss** (23 years old) - motorcyclist and automotive lifestyle content creator. The project involves generating realistic AI photographs for social media (TikTok, Instagram) and premium content (Fanvue).

## Project Structure

```
AI/
├── README.md                 # This file
├── CHARACTER_BIBLE.md        # Complete character description (appearance, style, personality)
├── CONTENT_STRATEGY.md       # Content strategy for social media
├── LORA_TRAINING_GUIDE.md    # LoRA model training guide for consistent appearance
├── PROMPTS_SFW.md            # SFW prompts (lifestyle, moto, selfie, outdoor)
├── PROMPTS_NSFW.md           # NSFW prompts (Fanvue exclusive, tiers 1-3)
├── PROMPTS_VEHICLES.md       # Vehicle prompts (solo, with character, details)
├── MONETIZATION.md           # Monetization strategy and revenue plans
├── POSTING_CALENDAR.md       # Weekly/monthly posting calendar
├── CAPTIONS_TEMPLATES.md     # Caption templates and hashtags
├── REVA_VOICE.md             # Communication profile (how Reva speaks/writes)
├── TROUBLESHOOTING.md        # AI generation troubleshooting guide
├── BRAND_PARTNERSHIPS.md     # Brand collaboration strategy
├── TOOLS_RESEARCH.md         # AI tools research (Stable Diffusion, Flux, etc.)
├── TODO.md                   # Project roadmap and task tracking
├── AI_TOOLS_COMPARISON.md    # AI tools comparison (Foxy, Higgsfield, ZenCreator, etc.)
├── CLAUDE.md                 # Instructions for Claude AI assistant
├── .claude/                  # Claude memory and decisions
│   ├── memory.md             # Persistent project memory
│   ├── decisions.md          # Decision log
│   └── style-guide.md        # Style guide
└── reference-photos/         # Reference photos for training and style
    ├── motorcycle/           # Kawasaki Ninja H2 (19x .avif + 19x .png + INFO.md)
    ├── car/                  # BMW M5 F90 (34x .jpg + INFO.md)
    ├── helmet/               # AGV Pista GP RR (empty - TODO)
    ├── outfits/              # Clothing and style (empty - TODO)
    └── environments/         # Photo environments (empty - TODO)
```

## Vehicles

| Vehicle | Year | Key Features | License Plate (SK) |
|---------|------|-------------|-------------------|
| **Kawasaki Ninja H2** | 2015 | First Edition #39/50, 200 HP supercharged, 76 km, Akrapovic, Brembo, Ohlins | BT-KWSH2 |
| **BMW M5 F90** | 2019 | 441 kW V8 xDrive, matte black wrap, Remus exhaust, yellow angel eyes | XX-BMWM5 |

> License plates are never shown readable in photos. Only the blue EU strip with SK may be visible.

## Changelog

### 2026-03-20 - Project Setup
- Created CHARACTER_BIBLE.md - complete Reva Voss description (appearance, personality, background, outfits)
- Created CONTENT_STRATEGY.md - content plan for TikTok/IG/Fanvue
- Created LORA_TRAINING_GUIDE.md - technical guide for training custom LoRA model
- Created PROMPTS_SFW.md - 10 SFW prompts (motorcycle, selfie, outdoor, cafe, fitness)
- Created PROMPTS_NSFW.md - 6 NSFW prompts in 3 tiers + Fanvue pricing strategy
- Created TOOLS_RESEARCH.md - overview of AI generation tools and checkpoints
- Created reference-photos/ structure for reference images

### 2026-03-20 - Reference Photos & Vehicles
- Uploaded Kawasaki Ninja H2 reference photos (19 pcs from Schneider Motorradzentrum DE)
- Uploaded BMW M5 F90 reference photos (34 pcs from Auto Exclusive Slovakia, Pezinok)
- Converted AVIF → PNG for better compatibility (motorcycle/)
- Created INFO.md files with technical specs for both vehicles
- Created PROMPTS_VEHICLES.md - 25+ prompts for both vehicles:
  - 5x solo Ninja H2 (garage, mountains, night, engine/cockpit details)
  - 6x solo BMW M5 (studio, night, highway, mountains, front/rear details)
  - 6x Reva + Ninja H2 (garage, urban, riding, helmet off, gas station, repair)
  - 6x Reva + BMW M5 (studio, hood, driver, exit, night drive, cafe)
  - 2x both vehicles together (garage collection, morning departure)
- Slovak license plates: BT-KWSH2 (motorcycle), XX-BMWM5 (car) - blur/hide rules

### 2026-03-21 - Claude Configuration & Business Documents
- Created CLAUDE.md - main instructions for Claude AI assistant
- Created .claude/memory.md - persistent memory (vehicles, project state, preferences)
- Created .claude/decisions.md - decision log with template
- Created .claude/style-guide.md - visual identity, prompt templates, social formats
- Created MONETIZATION.md - Fanvue tiers, revenue targets, costs, KPIs
- Created POSTING_CALENDAR.md - weekly plan, seasonal content, batching strategy
- Created CAPTIONS_TEMPLATES.md - caption templates for IG/TikTok/Fanvue/Reddit + hashtag database
- Created REVA_VOICE.md - communication profile, vocabulary, reactions, red lines
- Created TROUBLESHOOTING.md - solutions for face, hands, vehicles, plates, lighting, quality
- Created BRAND_PARTNERSHIPS.md - potential partners, pitch templates, partnership formats
- Converted all .md files from Slovak to English
- Created TODO.md - complete project roadmap with 7 phases, daily operations checklist
- Created AI_TOOLS_COMPARISON.md - comparison of Foxy AI, Higgsfield, ZenCreator, InfluencerStudio, SynthLife, SDXL
- Recommended tool stack: Foxy AI (SFW photos) + ZenCreator (NSFW) + Higgsfield (videos)

### 2026-03-21 - Character Redesign
- Hair: Changed from dark brunette to silver/platinum with dark roots (mirrors Ninja H2 chrome)
- Added signature makeup: smoky eye + sharp winged eyeliner (always present)
- Added 5 tattoo locations: behind left ear (moon), left arm sleeve (geometric/mechanical), right hand fingers (stick-and-poke), sternum (ornamental mandala), lower belly/hip (snake+flowers)
- Updated all prompt files (SFW, NSFW, Vehicles) with new character description
- Updated CLAUDE.md, style-guide.md, memory.md with new appearance
- Added tattoo troubleshooting section to TROUBLESHOOTING.md
- Updated pre-publishing checklist with makeup and tattoo checks
