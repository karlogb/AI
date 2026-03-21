# Troubleshooting - Common Issues & Solutions

> Common problems encountered during AI content generation and their solutions.
> Update whenever a new problem and solution is found.

---

## Face & Consistency

### Issue: Face changes between generations
**Cause:** Insufficient LoRA weight or missing face reference
**Solution:**
- Use "triple stack": LoRA (weight 0.6-0.7) + PuLID (0.8) + ControlNet OpenPose
- Always include detailed face description in prompt
- Reference image via IP-Adapter FaceID
- Seed locking for similar results

### Issue: Eyes have wrong color
**Cause:** Model defaults to brown/blue eyes
**Solution:**
- Explicitly in prompt: `hazel-green eyes, green-hazel iris`
- In negative prompt: `blue eyes, brown eyes, dark eyes`
- Increase weight: `(hazel-green eyes:1.3)`

### Issue: Hair is too long/short/straight
**Cause:** Vague hair description
**Solution:**
- Precise description: `dark brunette wavy hair, shoulder-length, natural waves`
- Negative: `straight hair, curly hair, long hair, short hair, blonde`
- Weight: `(shoulder-length dark wavy hair:1.2)`

### Issue: Freckles not visible
**Cause:** Model ignores them at lower resolution
**Solution:**
- `(light freckles across nose and cheeks:1.2)`
- Generate at higher resolution (min 1024x1024)
- ADetailer for face refinement

---

## Hands & Anatomy

### Issue: Deformed hands / extra fingers
**Cause:** Classic SD issue, especially with complex poses
**Solution:**
- Negative prompt: `bad hands, extra fingers, missing fingers, fused fingers, deformed hands, mutated hands`
- ControlNet OpenPose for correct pose
- ADetailer with "hand" detection
- Generate multiple variants and pick the best
- Inpainting to fix hands

### Issue: Anatomy is "off" (proportions)
**Cause:** Incorrect aspect ratio or complex pose
**Solution:**
- ControlNet OpenPose or DWPose
- Reference pose from real photo
- `(correct human anatomy:1.2)` in prompt
- Avoid extreme camera angles

---

## Vehicles

### Issue: Motorcycle doesn't look like Ninja H2
**Cause:** Model doesn't know the specific model
**Solution:**
- Detailed description: `Kawasaki Ninja H2, mirror black chrome fairings, green trellis frame, supercharger badge visible, Akrapovic carbon exhaust`
- IP-Adapter with motorcycle reference photo
- ControlNet Canny/Depth from reference photo
- LoRA trained on H2 photos (if available)

### Issue: BMW M5 has wrong details
**Cause:** Model mixes different M5 generations
**Solution:**
- Specify: `BMW M5 F90 2019, matte black wrap, yellow angel eye headlights, black wheels, blue M brake calipers`
- Reference photos via IP-Adapter
- ControlNet for correct shape

### Issue: License plate is readable!
**Cause:** Model generates realistic text on plates
**Solution (CRITICAL):**
- ALWAYS in negative prompt: `(readable text on license plate:1.5), (visible license plate text:1.3), (clear license plate:1.3)`
- Composition: plate out of frame, in shadow, blurred
- Post-processing: Blur plate in editor
- Inpainting: Override plate area
- Motion blur effect on entire vehicle

---

## Lighting & Colors

### Issue: Flat, boring lighting
**Cause:** Missing specific lighting prompt
**Solution:**
- Always specify lighting: `dramatic side lighting, neon red glow, golden hour sunlight, moody low-key lighting`
- Add light source: `lit by neon signs, single overhead light, window light`
- Negative: `flat lighting, overexposed, evenly lit`

### Issue: Colors are too saturated / unrealistic
**Cause:** Model "AI look"
**Solution:**
- `raw photo, film grain, natural colors, muted tones`
- Lower CFG scale (7-8 instead of 10+)
- Post-processing: slight desaturation
- Negative: `oversaturated, HDR, hyperrealistic colors`

### Issue: Skin tone is inconsistent
**Cause:** Different lighting conditions
**Solution:**
- Always: `light olive skin tone, warm undertone, Mediterranean complexion`
- Negative: `pale skin, dark skin, tan, sunburn`
- Consistent lighting setup between sets

---

## Quality & Artifacts

### Issue: Blurry details / low quality output
**Cause:** Low resolution or insufficient steps
**Solution:**
- Generate min 1024x1024, upscale to 2048+
- Min 30 sampling steps (DPM++ 2M Karras)
- Hires fix with 0.5-0.7 denoise
- 4x-UltraSharp upscaler

### Issue: "AI look" - too perfect, plastic
**Cause:** Over-quality without imperfections
**Solution:**
- Add: `raw photo, film grain, slight imperfections, pores visible, natural skin texture`
- Lower CFG (7-9)
- Photorealistic checkpoint (RealVisXL, Juggernaut)
- Negative: `airbrushed, plastic skin, perfect skin, smooth skin`

### Issue: Watermark / text artifacts
**Cause:** Training data contamination
**Solution:**
- Negative: `watermark, text, signature, logo, username, copyright`
- Clean checkpoint without NSFW merge issues

---

## Environments

### Issue: Garage doesn't look realistic
**Cause:** Vague description
**Solution:**
- Detailed prompt: `industrial garage interior, concrete floor with oil stains, exposed brick walls, tool wall with wrenches and sockets, red neon LED strip light, motorcycle hydraulic lift, dirty workbench`
- Reference photo via ControlNet Depth

### Issue: Outdoor scene doesn't look like Slovakia
**Cause:** Model has no concept of Slovak roads
**Solution:**
- `European mountain road, alpine scenery similar to Alps, coniferous forest, Tatra mountains, winding asphalt road, European road markings`
- Reference photos of Slovak roads
- Post-processing: Color grade for "European" look

---

## Workflow Issues

### Issue: Generation takes too long
**Solution:**
- Batch generation: multiple images at once
- Lower resolution for drafts, upscale only finals
- Cloud GPU (RunPod) if local HW can't keep up
- Lower sampling steps for test generations (15-20)

### Issue: VRAM out of memory
**Solution:**
- Lower batch size to 1
- Use --medvram or --lowvram flag
- FP16 precision
- Disable unnecessary extensions
- Close other GPU applications

### Issue: ControlNet has no effect
**Solution:**
- Check preprocessor output (preview)
- Increase ControlNet weight (0.8-1.0)
- Correct model for correct preprocessor (OpenPose for poses, Canny for edges)
- Control mode: "Balanced" or "ControlNet is more important"

---

## Pre-Publishing Checklist

- [ ] Face is consistent with CHARACTER_BIBLE
- [ ] Eyes are hazel-green
- [ ] Hair is dark, wavy, shoulder-length
- [ ] Freckles visible (if close-up)
- [ ] Nose stud on left side
- [ ] Hands look normal (5 fingers on each)
- [ ] License plate is NOT readable
- [ ] Vehicle matches description
- [ ] Lighting is moody/dramatic
- [ ] No AI artifacts (watermark, text, deformations)
- [ ] Correct aspect ratio for platform
- [ ] No NSFW on SFW platforms
