# Reva Voss - SFW Generation Prompts

## Base Character Prompt (always use as foundation)

```
A 24-year-old woman, athletic slim hourglass figure, dark brunette wavy hair
shoulder-length, hazel-green eyes, light olive skin, full natural lips, thick
natural eyebrows, straight delicate nose, light freckles across nose, small
crescent moon tattoo behind left ear, small silver nose stud on left nostril.
```

---

## Category 1: Motorcycle Photos

### With motorcycle - static
```
[CHARACTER PROMPT], wearing black leather motorcycle jacket, black leather pants,
standing next to a Kawasaki Ninja H2 supercharged sport motorcycle in mirror black
paint with green tint, Akrapovic exhaust, in an industrial garage with concrete
floor and brick walls, neon red ambient lighting, motorcycle gear on the wall,
confident pose, looking at camera, photorealistic, shot on Canon R5, 85mm f/1.4,
shallow depth of field
```

### Holding helmet
```
[CHARACTER PROMPT], holding an AGV Pista GP RR helmet matte black with red accents
under her arm, wearing black leather motorcycle jacket unzipped slightly, black
crop top underneath, standing on empty mountain road at golden hour, Kawasaki Ninja
H2 parked behind her, wind in hair, natural lighting, photorealistic, editorial
photography style
```

### Riding POV (side angle)
```
[CHARACTER PROMPT], riding a Kawasaki Ninja H2 sport motorcycle on a winding
mountain road, wearing full black motorcycle gear, AGV Pista GP RR matte black
helmet with red accents, aggressive sport riding position, motion blur background,
golden hour sunlight, dynamic action shot, photorealistic
```

### Sitting on motorcycle (casual)
```
[CHARACTER PROMPT], sitting sideways on a Kawasaki Ninja H2 motorcycle, wearing
black crop top, high-waist jeans, white Nike Air Force 1 sneakers, holding AGV
helmet, at a retro gas station at sunset, relaxed confident pose, photorealistic,
lifestyle photography
```

---

## Category 2: Mirror Selfie (Bedroom)

### Classic mirror selfie
```
[CHARACTER PROMPT], taking a mirror selfie in a modern minimalist bedroom,
holding iPhone 17 Pro in Orange color with clear case, wearing
oversized black Metallica t-shirt, grey jogger shorts, LED strip warm white
lights on the wall, grey/white walls, bed with white sheets and black throw
blanket visible, monstera plant in corner, motorcycle helmet on nightstand,
natural relaxed expression, slightly messy hair, realistic phone selfie quality
```

### GRWM (Getting Ready With Me)
```
[CHARACTER PROMPT], getting ready in front of a large mirror in modern minimalist
bedroom, wearing white tank top, applying minimal makeup, natural morning light
from window, warm tones, iPhone 17 Pro Orange on the desk,
motorcycle keys visible, cozy authentic vibe, candid shot, photorealistic
```

---

## Category 3: Bathroom Selfie

### Post-shower casual
```
[CHARACTER PROMPT], mirror selfie in modern bathroom with white tiles and wooden
accents, wet wavy hair, wearing white towel wrapped, warm lighting, steamy
atmosphere, iPhone 17 Pro Orange in hand with clear case, natural
no-makeup look, relaxed expression, photorealistic
```

### Morning routine
```
[CHARACTER PROMPT], in a modern bathroom, white with wooden accents, brushing
teeth, wearing oversized grey t-shirt, messy morning hair, warm lighting,
candid authentic moment, photorealistic, lifestyle photography
```

---

## Category 4: Outdoor / Travel

### Mountain road
```
[CHARACTER PROMPT], standing on a scenic mountain road overlook, wearing black
leather motorcycle jacket open, white crop top, black jeans, Kawasaki Ninja H2
parked on the road, dramatic mountain landscape, golden hour, wind blowing hair,
epic cinematic composition, photorealistic, shot on Sony A7IV
```

### Night ride cityscape
```
[CHARACTER PROMPT], standing next to Kawasaki Ninja H2 motorcycle on a city
bridge at night, wearing black leather jacket, neon city lights reflecting,
urban night atmosphere, cinematic lighting, blue and red ambient light,
photorealistic
```

---

## Category 5: Cafe / Lifestyle

### At a cafe
```
[CHARACTER PROMPT], sitting in a modern industrial-style cafe, drinking coffee,
wearing black crop top, high-waist jeans, black baseball cap, relaxed pose,
Kawasaki Ninja H2 visible through the window parked outside, warm indoor
lighting, candid lifestyle photography, photorealistic
```

### Workout / Fitness
```
[CHARACTER PROMPT], doing a home workout in modern minimalist living room,
wearing black sports bra, black leggings, toned athletic body, mid-exercise
pose, natural lighting, fitness photography, photorealistic
```

---

## Negative Prompt (always use)

```
(deformed, distorted, disfigured:1.3), poorly drawn, bad anatomy, wrong anatomy,
extra limb, missing limb, floating limbs, (mutated hands and fingers:1.4),
disconnected limbs, mutation, mutated, ugly, disgusting, blurry, amputation,
extra fingers, fewer fingers, bad hands, text, watermark, signature, logo,
tattoo on face, unrealistic skin, plastic looking, anime, cartoon, painting,
illustration, 3d render
```

---

## Generation Notes

1. **Always start with character prompt** - ensures consistency
2. **Always use negative prompt** - prevents deformations
3. **CFG Scale**: 7-8 for realistic results
4. **Steps**: 30-40 for quality
5. **Sampler**: DPM++ 2M Karras or Euler a
6. **Resolution**: 768x1024 (portrait) or 1024x768 (landscape)
7. **After training LoRA**: add `<lora:reva_voss:0.7-0.85>` to prompt
