# Memory - Project Persistent Memory

> This file contains facts, preferences, and information gathered during work.
> Update whenever new information is learned.

## User
- Communicates in Slovak
- Owns both vehicles (Kawasaki Ninja H2 + BMW M5)
- Wants to create an AI influencer in the moto/automotive niche
- Prefers concise, efficient communication
- Pushes photos directly to main branch, Claude works on feature branches
- All .md files should be written in English

## Project Status
- **Phase:** Preparation (character bible, prompts, reference photos)
- **Next steps:** LoRA model training, first image generation
- **Missing:** Reference photos for helmet, outfits, environments

## Vehicles - Details

### Kawasaki Ninja H2
- **First Edition #39 of 50** units from the first series to Germany
- Year 2015, 76 km driven (practically new)
- 998 cc, 147 kW (200 HP), supercharged inline-4
- Mirror black chrome paint, green trellis frame
- Akrapovic carbon exhaust, Brembo brakes, Ohlins steering damper
- Short license plate holder, mini blinkers, Bursig center stand
- Sold by Schneider Motorradzentrum (Germany)
- License plate: BT-KWSH2 (Slovak square format)
- 19 reference photos (.avif + .png conversion)

### BMW M5 F90
- Year 2019, 90,336 km
- 4395 cc V8, 441 kW, xDrive 4x4, 8-speed automatic
- Matte black wrap, Remus exhaust system
- Yellow angel eyes, black wheels, blue M brake calipers
- Panoramic roof, head-up display, leather interior
- VIN: WBSJF01070G967982
- Sold by Auto Exclusive Slovakia, Pezinok
- License plate: XX-BMWM5 (Slovak long EU format)
- 34 reference photos (.jpg)

## Technical Notes
- AVIF photos need conversion to PNG for better compatibility (heif-convert)
- Some AVIF files are too large for direct reading (>256KB)
- JPG photos of BMW are fine for direct display (~100-230KB)

## Preferred Tools & Models (from TOOLS_RESEARCH.md)
- Stable Diffusion XL + LoRA for consistency
- RealVisXL / Juggernaut XL as base checkpoints
- Flux for highest quality (if available)
