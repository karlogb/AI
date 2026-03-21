# CLAUDE.md - Project Instructions

## Project
This is the **Reva Voss** project - an AI-generated virtual influencer (motorcyclist / automotive lifestyle). The goal is to create consistent, realistic AI-generated content for social media and premium platforms.

## Language
- Communication with user: **Slovak**
- Files and documentation: **English**
- Commit messages: English
- PR descriptions: English

## Commit & PR Rules
- Every commit must have a clear, descriptive message
- Every Pull Request MUST have a proper title + description with:
  - What was done and why
  - List of specific changes
  - Any future TODOs
- README.md changelog is updated with every major change
- Branch naming: `claude/<description>-<session-id>`

## Project Structure
```
AI/
├── CLAUDE.md                 # These instructions (read first!)
├── README.md                 # Project description + changelog
├── CHARACTER_BIBLE.md        # Appearance, personality, backstory
├── CONTENT_STRATEGY.md       # Content strategy for platforms
├── LORA_TRAINING_GUIDE.md    # Technical LoRA training guide
├── PROMPTS_SFW.md            # SFW prompts for generation
├── PROMPTS_NSFW.md           # NSFW prompts (Fanvue exclusive)
├── PROMPTS_VEHICLES.md       # Vehicle prompts
├── MONETIZATION.md           # Monetization strategy and revenue plans
├── POSTING_CALENDAR.md       # Weekly/monthly posting calendar
├── CAPTIONS_TEMPLATES.md     # Caption templates and hashtags
├── REVA_VOICE.md             # Communication profile - how Reva speaks/writes
├── TROUBLESHOOTING.md        # Troubleshooting AI generation issues
├── BRAND_PARTNERSHIPS.md     # Brand collaboration strategy
├── TOOLS_RESEARCH.md         # AI tools overview
├── TODO.md                   # Project roadmap and task tracking
├── AI_TOOLS_COMPARISON.md    # AI tools comparison for content creation
├── .claude/
│   ├── memory.md             # Persistent memory - project facts
│   ├── decisions.md          # Decision log and reasoning
│   └── style-guide.md        # Style guide for consistency
└── reference-photos/
    ├── motorcycle/           # Kawasaki Ninja H2 reference photos
    ├── car/                  # BMW M5 F90 reference photos
    ├── helmet/               # Helmet references (TODO)
    ├── outfits/              # Outfit references (TODO)
    └── environments/         # Environment references (TODO)
```

## Key Rules

### Character - Reva Voss
- 23 years old (born August 2, 2003, Leo ♌), athletic build
- Hair: Silver/platinum with dark roots, shoulder-length, slightly wavy (mirrors Ninja H2 chrome)
- Hazel-green eyes, light olive skin, freckles across nose
- Makeup: Smoky eye + sharp winged eyeliner (signature), nude matte lips
- Tattoos: crescent moon (behind left ear), geometric sleeve (left arm), finger tattoos (right hand), sternum mandala, snake+flowers (hip)
- Silver nose stud on left nostril
- NEVER change physical attributes!

### Vehicles
| Vehicle | License Plate (SK) | Key Look |
|---------|-------------------|----------|
| Kawasaki Ninja H2 (2015) | BT-KWSH2 | Mirror black chrome, green frame, Akrapovic |
| BMW M5 F90 (2019) | XX-BMWM5 | Matte black wrap, yellow angel eyes, Remus |

### License Plate Rules (CRITICAL!)
- License plates are NEVER shown readable in photos
- Allowed: blurred, in shadow, cropped, too far away
- EU blue strip with SK may be visible
- Always in negative prompt: `(readable text on license plate:1.5)`

### Helmet
- AGV Pista GP RR, matte black with red accents

### Phone
- iPhone 17 Pro, Orange, clear case

### Environments
- Garage: industrial, concrete, brick, neon red light
- Bedroom: minimalist, grey/white, LED strips, monstera
- Bathroom: white + wooden accents
- Outdoor: Slovak mountains, Bratislava old town

## Workflow
1. Before any work, read CLAUDE.md + .claude/memory.md
2. Check decisions.md for previous decisions
3. Follow style-guide.md for consistency
4. Update memory.md if you learn something new
5. Record important decisions in decisions.md
6. Update README.md changelog
7. Commit and push with proper description
