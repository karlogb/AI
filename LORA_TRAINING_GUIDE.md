# Reva Voss - LoRA Training Guide

## What is LoRA and Why We Need It

LoRA (Low-Rank Adaptation) is a technique for fine-tuning an AI model on a specific visual -
in our case, Reva's face. After training a LoRA, we can generate consistent photos with the
same face, body type, and features every time.

---

## Step 1: Prepare "Seed" Images

### Generating Base Reference Photos

Before training a LoRA, we need 15-30 high-quality reference images of our character.

**Process:**
1. Generate 100+ images using the character prompt from `PROMPTS_SFW.md`
2. Select 15-30 best ones where the face is consistent
3. Alternative: use PuLID/IP-Adapter to "lock" the face from a single seed image

### Training Dataset Requirements:
- **Count**: 15-30 images (ideally 20-25)
- **Resolution**: Minimum 512x512, ideally 768x1024
- **Diversity**:
  - 5x close-up face (various angles - front, 3/4, profile)
  - 5x half body (different clothing)
  - 5x full body (different poses)
  - 5x different lighting (daylight, artificial, outdoor, indoor)
  - Rest: mix
- **Backgrounds**: Varied (not always the same)
- **Clothing**: Varied (so the LoRA learns the face, not the outfit)

### Captioning:
Every image needs a text description. Use:
- **BLIP-2** or **WD Tagger** for automatic captioning
- Manually edit - add trigger word

---

## Step 2: Training Setup

### Recommended Software:
| Tool | Use Case | Link |
|------|----------|------|
| **Kohya_ss** | Most widely used LoRA trainer | github.com/bmaltais/kohya_ss |
| **LoRA Easy Training Scripts** | Simpler alternative | github.com/derrian-distro/LoRA_Easy_Training_Scripts |
| **ai-toolkit** | Modern, supports FLUX | github.com/ostris/ai-toolkit |

### Training Parameters (SDXL):

```yaml
# Basic settings
model_type: SDXL
network_type: LoRA
network_rank: 32          # dim (higher = more detail, but slower)
network_alpha: 16          # typically rank/2
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

### Training Parameters (FLUX):

```yaml
# For FLUX models
model_type: FLUX.1-dev  # or FLUX.2
network_type: LoRA
network_rank: 16-32
learning_rate: 4e-4
optimizer: Prodigy       # or AdamW
batch_size: 1-2
resolution: 1024
steps: 1500-3000
trigger_word: "reva_voss"
```

---

## Step 3: Training

### Local (if you have a GPU):
- **Minimum**: RTX 3060 12GB VRAM
- **Recommended**: RTX 4070 Ti+ / 16GB+ VRAM
- **Time**: 30-90 minutes (depends on GPU and dataset)

### Cloud (if you don't have a GPU):
| Service | Cost | VRAM |
|---------|------|------|
| RunPod | ~$0.40/hr | 24-48GB |
| Vast.ai | ~$0.30/hr | 24-48GB |
| Google Colab Pro | $10/month | 15-40GB |
| CivitAI Training | Varies | Managed |

---

## Step 4: Testing and Iteration

### Test Prompt:
```
reva_voss, a woman, portrait photo, looking at camera, natural lighting,
neutral background, photorealistic
```

### What to Check:
- [ ] Face is consistent
- [ ] Eyes are correct color (hazel-green)
- [ ] Hair is correct color and length
- [ ] Freckles are present
- [ ] Nose piercing is visible
- [ ] Not "overfit" (too similar poses/backgrounds)
- [ ] Not "underfit" (face is unstable)

### LoRA Strength:
- **0.6-0.7**: Softer likeness (more variability)
- **0.7-0.85**: Optimal (good likeness + flexibility)
- **0.85-1.0**: Very strong likeness (risk of overfitting, less flexibility)

**Recommended**: `<lora:reva_voss:0.75>`

---

## Step 5: Production Use

### In prompt:
```
reva_voss, [rest of prompt], <lora:reva_voss:0.75>
```

### Combining with other techniques:
- **LoRA + IP-Adapter**: Even stronger consistency
- **LoRA + PuLID**: For face fine-tuning
- **LoRA + ControlNet**: For specific poses

---

## Alternative: Without LoRA (faster but less consistent)

If you don't want to train a LoRA, you can use:

### PuLID + FLUX Kontext
1. Generate one "seed" photo of Reva
2. Use PuLID for every subsequent generation with reference to the seed
3. Advantage: No training required
4. Disadvantage: Less consistent than LoRA

### IP-Adapter Face
1. Same principle - reference photo
2. IP-Adapter FaceID transfers facial features
3. Can be combined with LoRA

### FLUX Kontext (Character Reference)
1. FLUX.2 supports character reference natively
2. Upload reference photo and the model will try to preserve the face
3. Works without training

---

## Recommended Workflow

```
1. Generate 100+ photos with character prompt (SDXL/FLUX)
     ↓
2. Select 20-25 best ones (consistent face)
     ↓
3. Captioning (BLIP-2 + manual editing)
     ↓
4. Train LoRA (Kohya_ss / ai-toolkit)
     ↓
5. Test on various prompts
     ↓
6. Iterate (adjust dataset/parameters if needed)
     ↓
7. Production - generate content with LoRA
```
