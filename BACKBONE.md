# ZONEWISE PRODUCTION STUDIO — Complete Backbone

## Our Weapon Stack vs Hollywood

| Hollywood Team | Cost/Month | Our AI Agent | Cost/Month |
|---------------|-----------|-------------|-----------|
| Development Executive | $12,000 | BriefAgent (Dify + Gemini Flash) | $0 |
| Screenwriter | $8,000-15,000/script | ScriptwriterAgent (Dify + Gemini) | $0 |
| Script Doctor | $5,000/pass | ScriptEditorAgent (Dify + Ariel-Style RAG) | $0 |
| Storyboard Artist | $3,000-5,000 | StoryboardAgent (Nano Banana Pro + Stitch) | $0 |
| Director of Photography | $5,000-10,000/day | CinematographyAgent (Veo 3.1 + Three.js) | ~$5-15 |
| Film Editor | $4,000-8,000/week | EditorAgent (Remotion + Google Flow) | $0 |
| Sound Designer + Composer | $3,000-6,000 | AudioAgent (Google TTS + Lyria 3) | $0 |
| QA / Test Audience | $2,000-5,000 | QAAgent (TwelveLabs AI Vision) | $0 |
| **TOTAL** | **$42,000-66,000** | **8 AI Agents** | **~$37/mo** |

---

## BACKBONE 1: Cinematic Module Library (10 Modules)

Source: `zonewise-web/components/cinematic/` → copied to `zonewise-video/src/modules/cinematic/`

### CurtainReveal.tsx
- **What:** Split-screen curtain wipe transition between two scenes
- **Hollywood Equivalent:** Horizontal wipe transition (Star Wars style)
- **Used By:** EditorAgent, Motion Agent
- **Tech:** CSS clip-path animation driven by framer-motion
- **Video Use:** Scene 2→3 transition (spreadsheet chaos → ZoneWise map)

### HeroProperty3D.tsx + HeroProperty3DCanvas.tsx
- **What:** 3D rotating Florida property with auction elements
- **Hollywood Equivalent:** CG establishing shot (like house flyover in real estate shows)
- **Used By:** CinematographyAgent, Motion Agent
- **Tech:** @react-three/fiber + @react-three/drei, GLB model loading, OrbitControls
- **Video Use:** Scene 1 hero shot, rotating property with "FOR AUCTION" sign
- **Remotion Rule:** Drive ALL rotation from `useCurrentFrame()`, never Three.js internal clock

### KineticMarquee.tsx
- **What:** Horizontally scrolling text ticker with configurable speed
- **Hollywood Equivalent:** CNN-style lower-third news ticker
- **Used By:** Motion Agent, EditorAgent
- **Tech:** CSS transform animation, infinite scroll loop
- **Video Use:** Scene 4 pipeline steps scrolling, data tickers, breaking auction alerts

### MeshGradientBg.tsx
- **What:** Dynamic animated color gradient background
- **Hollywood Equivalent:** Abstract mood lighting / color wash backgrounds
- **Used By:** Motion Agent, CinematographyAgent
- **Tech:** Canvas-based mesh gradient with noise displacement
- **Video Use:** Background for dark scenes (pipeline, moat), mood setting

### ParticleButton.tsx
- **What:** Button that explodes into particles on interaction
- **Hollywood Equivalent:** VFX particle burst (confetti, sparks)
- **Used By:** Motion Agent
- **Tech:** Canvas particle system with physics simulation
- **Video Use:** Scene 7 CTA explosion — "Start Free" button bursts into particles

### StickyCards.tsx
- **What:** Scroll-pinned cards that stack as user progresses
- **Hollywood Equivalent:** Feature comparison montage with overlapping cards
- **Used By:** Motion Agent, EditorAgent
- **Tech:** GSAP ScrollTrigger pinning + stagger animation
- **Video Use:** Scene 5 persona cards (investor, realtor, attorney, homebuyer)

### TextMaskReveal.tsx
- **What:** Text appears through a mask/clip animation
- **Hollywood Equivalent:** Title card reveal (text slides in from behind a mask)
- **Used By:** Motion Agent
- **Tech:** CSS clip-path + framer-motion spring
- **Video Use:** Chapter titles, scene headers, key messages

### TextScramble.tsx
- **What:** Characters scramble/decode into final text (Matrix-style)
- **Hollywood Equivalent:** Hacker/tech reveal effect (like decryption sequences)
- **Used By:** Motion Agent
- **Tech:** Character-by-character randomization → resolve to target string
- **Video Use:** Scene 6 "13 Patent Claims" dramatic reveal, "Patent Pending" stamp

### ZoomParallax.tsx
- **What:** Multi-layer depth zoom creating parallax 3D effect
- **Hollywood Equivalent:** Dolly zoom / vertigo effect with depth layers
- **Used By:** Motion Agent, CinematographyAgent
- **Tech:** Scroll-driven transform with multiple z-depth layers
- **Video Use:** Scene 6 zoom into patent document, depth-of-field hero shots

### index.ts (Barrel Export)
- Clean re-exports all modules for single-line imports

---

## BACKBONE 2: Animation Component Library (5 Components)

Source: `zonewise-web/components/animations/` → copied to `zonewise-video/src/modules/animations/`

### AnimatedCounter.tsx
- **What:** Number countup animation (0 → target value)
- **Hollywood Equivalent:** Infographic number reveal (like in documentary stats)
- **Used By:** Motion Agent, EditorAgent
- **Video Use:** KPI countups — "67 counties", "13 patent claims", "$300K value"

### AnimatedSection.tsx
- **What:** Section-level entrance animation (fade-in, slide-up)
- **Hollywood Equivalent:** Scene entrance / establishing shot transition
- **Used By:** EditorAgent
- **Video Use:** Each new scene's first frame entrance

### GlowButton.tsx
- **What:** Button with animated glow/pulse effect
- **Hollywood Equivalent:** Neon sign / highlighted CTA
- **Used By:** Motion Agent
- **Video Use:** Scene 7 CTA "Start Free at zonewise.ai" with pulsing glow

### MeshGradient.tsx
- **What:** Standalone mesh gradient animation (lighter than MeshGradientBg)
- **Hollywood Equivalent:** Abstract background plate
- **Used By:** CinematographyAgent
- **Video Use:** Subtle backgrounds for text-heavy scenes

### StaggerChildren.tsx
- **What:** Sequential child element reveals with configurable delay
- **Hollywood Equivalent:** Bullet point build animation in presentations
- **Used By:** Motion Agent, EditorAgent
- **Video Use:** Scene 4 pipeline steps appearing one by one, feature lists

---

## BACKBONE 3: Google Production Tools (Business Plus — $26.40/mo)

### Nano Banana Pro (Gemini 3 Pro Image)
- **What:** State-of-the-art AI image generation, 4K, up to 14 reference images
- **Hollywood Equivalent:** Concept artist + matte painter + graphic designer
- **Used By:** CinematographyAgent, StoryboardAgent, Media Scout
- **Capabilities:**
  - Generate photorealistic scene backgrounds
  - Create consistent branded visuals (14 ref images = full brand kit)
  - Infographics with accurate text rendering in multiple languages
  - Product mockups, UI screenshots, persona portraits
  - 4K resolution for print-quality assets
- **API:** `generativelanguage.googleapis.com/v1beta/models/gemini-3.1-flash-image-preview`
- **Cost:** Included via Google Workspace, ~$0.04/image via API

### Veo 3.1 (AI Video Generation)
- **What:** Text-to-video with native audio, 8s clips, 1080p, lip sync
- **Hollywood Equivalent:** B-roll camera crew + drone operator + stock footage library
- **Used By:** CinematographyAgent, Media Scout
- **Capabilities:**
  - Generate 8-second video clips from text descriptions
  - Native audio generation (ambient sounds, speech, effects)
  - Camera controls (aerial, tracking, close-up, pan)
  - Style transfer and scene extension via Google Flow
  - Vertical (9:16) and landscape (16:9) output
- **Variants:**
  - Veo 3.1 Standard: highest quality, 10 free/month
  - Veo 3.1 Fast: faster generation, lower cost
  - Veo 3.1 Lite: batch processing at 50% cost
- **API:** Vertex AI API + Google Vids

### Google Cloud TTS (Gemini 2.5 Flash TTS)
- **What:** Professional text-to-speech with 30 voices, multi-speaker support
- **Hollywood Equivalent:** Professional voiceover narrator
- **Used By:** AudioAgent
- **Capabilities:**
  - 30 built-in voices (Kore, Orus, Puck, Charon, etc.)
  - Multi-speaker dialogue (podcast-style)
  - Emotion and pacing control via prompt
  - 24kHz PCM output → WAV/MP3 conversion
  - Language support: 24 languages
- **API:** `generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-tts`
- **Cost:** Included via API key
- **VERIFIED:** 82-second voiceover generated and committed to repo

### Lyria 3 (AI Music Composition)
- **What:** Custom music generation from text descriptions
- **Hollywood Equivalent:** Film score composer + music licensing library
- **Used By:** AudioAgent
- **Capabilities:**
  - Generate background music per scene mood
  - Corporate, cinematic, energetic, ambient styles
  - No licensing fees — royalty-free generated music
  - Custom duration matching video length
- **Access:** Google Vids integration, Google AI Pro/Ultra

### Google Stitch (AI UI Design)
- **What:** AI-native design canvas — text-to-UI with React code export
- **Hollywood Equivalent:** UI/UX designer for screen recordings and mockups
- **Used By:** StoryboardAgent, Media Scout
- **Capabilities:**
  - 350 free generations/month
  - Voice interaction (speak design direction)
  - Multi-screen prototyping (5 screens at once)
  - Export to React code + Figma format
  - DESIGN.md brand spec support
  - MCP server for Claude Code integration
- **Access:** stitch.withgoogle.com (free with Google account)

### Google Flow (AI Video Editing)
- **What:** AI-powered video editing with Veo 3.1 integration
- **Hollywood Equivalent:** Film editor's editing suite (Premiere Pro / DaVinci)
- **Used By:** EditorAgent
- **Capabilities:**
  - Scene extension (make clips longer with AI)
  - AI camera controls (adjust angles, zoom, movement post-generation)
  - Style transfer across scenes
  - Character consistency
  - Timeline management
- **Access:** flow.google.com (free)

### Google Vids (Video Assembly)
- **What:** Video editing suite with Veo 3.1 + Lyria 3 integration
- **Hollywood Equivalent:** Quick-cut editing room
- **Used By:** EditorAgent, AudioAgent
- **Capabilities:**
  - 10 free Veo video generations/month (1,000 on Ultra)
  - Lyria 3 music generation
  - AI avatars for presenting
  - Screen recording via Chrome extension
  - Direct YouTube publishing
- **Access:** vids.new (included in Workspace)

---

## BACKBONE 4: Third-Party Production Tools

### Remotion (Programmatic Video Engine)
- **What:** React-based video rendering framework
- **Hollywood Equivalent:** The rendering farm / final output pipeline
- **Used By:** EditorAgent, ALL agents (final render)
- **Capabilities:**
  - Programmatic video from React components
  - Frame-accurate animations via `useCurrentFrame()`
  - Audio sync with `<Audio>` + `<OffthreadVideo>`
  - `<TransitionSeries>` for scene transitions
  - `@remotion/three` for 3D content
  - `@remotion/light-leaks` for cinematic overlays
  - `@remotion/lottie` for After Effects animations
  - `@remotion/google-fonts` for typography
  - Batch rendering via GHA / Hetzner
  - Export: MP4 (H.264), WebM, GIF, transparent video
- **Cost:** Free (<4 employees)

### ElevenLabs (Premium Voice)
- **What:** Advanced TTS with voice cloning, word-level alignment
- **Hollywood Equivalent:** A-list voice actor
- **Used By:** AudioAgent
- **Capabilities:**
  - 21+ premium voices (Eric = Smooth/Trustworthy for product demos)
  - Word-level character alignment (ms-precision sync)
  - Voice cloning (future: Ariel's own voice)
  - Multi-language support
  - 10,000 free characters/month
- **API Key:** LIVE in GitHub secrets
- **Note:** Datacenter IPs blocked on free tier — use Ariel's device or upgrade to Starter ($5/mo)

### Pexels (Stock Footage)
- **What:** Free HD stock video and photo library
- **Hollywood Equivalent:** Stock footage house (Getty, Shutterstock)
- **Used By:** Media Scout
- **Capabilities:**
  - Unlimited free HD video downloads
  - Search by keyword, orientation, color
  - 200 requests/hour API limit
  - Florida aerial, courthouse, real estate footage available
- **API Key:** LIVE in GitHub secrets

### TwelveLabs (Video AI Vision)
- **What:** AI that watches and understands video content
- **Hollywood Equivalent:** Test audience + continuity supervisor
- **Used By:** QAAgent (Post Producer)
- **Capabilities:**
  - Semantic video search ("find the scene where...")
  - Scene detection and classification
  - Object/person recognition
  - Quality scoring (pacing, audio sync, visual coherence)
  - 600 minutes free indexing
- **Status:** Account created, API key pending (desktop-only generation)

### Mapbox (Geographic Visualization)
- **What:** Interactive map rendering with 3D buildings and camera animation
- **Hollywood Equivalent:** Geographic VFX (like CNN election maps)
- **Used By:** Motion Agent, CinematographyAgent
- **Capabilities:**
  - 67 Florida county boundaries
  - 3D building rendering
  - Camera animation along routes (turf.js)
  - Markers, labels, custom styling
  - Render with `--gl=angle --concurrency=1` for Remotion
- **Token:** LIVE in GitHub secrets (pk.eyJ1...clmhmCnTw)
- **Remotion Rules:** Full integration via remotion-dev/skills/remotion/rules/maps.md

---

## BACKBONE 5: Adopted Knowledge Bases (3 Repos)

### remotion-dev/skills (REPOEVAL: 100/100)
- **Stars:** 2,541 | **Updated:** Today | **License:** Free
- **30 rule files that give our agents Remotion mastery:**
  - `3d.md` — Three.js in Remotion (ThreeCanvas, frame-driven animation)
  - `maps.md` — Mapbox camera animation, markers, 3D buildings
  - `transitions.md` — TransitionSeries, fade, slide, wipe, light-leak overlays
  - `text-animations.md` — Typewriter, word highlight, kinetic text
  - `charts.md` — Bar, pie, line, stock charts (SVG + D3)
  - `audio.md` — Volume, ducking, trimming, speed, pitch
  - `voiceover.md` — ElevenLabs TTS + calculateMetadata for dynamic duration
  - `captions-workflow.md` — TikTok-style animated subtitles
  - `light-leaks.md` — Cinematic light leak overlays (@remotion/light-leaks)
  - `lottie.md` — After Effects animations via @remotion/lottie
  - `images.md` — Ken Burns effect, spring reveals, layered compositions
  - `fonts.md` — Google Fonts loading
  - `sequencing.md` — Scene timing, delay, trim patterns
  - `timing.md` — Interpolation curves, spring physics, easing
  - `tailwind.md` — TailwindCSS in Remotion
  - `videos.md` — OffthreadVideo, trimming, looping
  - `audio-visualization.md` — Spectrum bars, waveforms, bass-reactive effects
  - `sfx.md` — Sound effect integration
  - + 12 more utility rules

### DojoCodingLabs/remotion-superpowers (REPOEVAL: 88/100)
- **Forked to:** breverdbidder/zonewise-superpowers
- **What it gives us:**
  - 3 production agents (Video Director, Media Scout, Post Producer)
  - 13 slash commands (/create-video, /add-voiceover, /add-captions, etc.)
  - 5 MCP server configs (remotion-media, ElevenLabs, TwelveLabs, Pexels, Replicate)
  - Claude Code plugin system (hooks, marketplace integration)
  - 18 production skill rules (pipeline, 3D, VFX, image gen, music scoring, etc.)
- **Our Delta:**
  - +2 agents (Motion Agent, Audio Agent)
  - +1 agent spec (BriefAgent, ScriptwriterAgent — Dify workflows)
  - Google tools replacing Replicate/Suno
  - DESIGN.md brand spec with 14 Nano Banana references
  - Updated plugin.json (v3.0.0 zonewise-superpowers)

### remotion-dev/template-prompt-to-video (REPOEVAL: 86/100)
- **Cherry-picked into:** zonewise-video
- **What it gives us:**
  - Timeline JSON schema (Zod-typed, ms-precision)
  - CLI pipeline: prompt → script → images → voiceover → timeline → render
  - ElevenLabs word-level character alignment integration
  - Slide-based composition pattern with background transitions
  - Audio sync with calculateMetadata for dynamic duration

---

## BACKBONE 6: Installed Dependencies

```yaml
# Animation & Motion
framer-motion: ^11.18.2        # React animation library (springs, gestures, layout)
gsap: ^3.14.2                  # GreenSock (ScrollTrigger, timelines, complex sequences)

# 3D Rendering
"@react-three/fiber": ^8.18.0  # React renderer for Three.js
"@react-three/drei": ^9.122.0  # Helpers (OrbitControls, Float, Text3D, Environment)
three: ^0.183.2                # 3D engine (WebGL)

# Remotion Core
remotion: ^4.0.0               # Programmatic video framework
"@remotion/three": ^4.0.0      # Three.js integration for Remotion
"@remotion/transitions": ^4.0.0 # TransitionSeries (fade, slide, wipe)
"@remotion/light-leaks": ^4.0.0 # Cinematic light leak overlays
"@remotion/lottie": ^4.0.0     # After Effects animation playback
"@remotion/google-fonts": ^4.0.0 # Typography loading
"@remotion/media": ^4.0.0      # Audio/video handling

# Maps
mapbox-gl: ^3.9.0              # Mapbox GL JS (67 FL county maps)
"@turf/turf": ^7.0.0           # Geographic calculations (line slicing, distances)

# Data Validation
zod: ^3.23.0                   # Runtime type checking for Timeline JSON schema
```

---

## BACKBONE 7: Infrastructure

### Dify (AI Agent Orchestration)
- **Location:** Hetzner 87.99.129.125, port 3000
- **Role:** Brain of the production studio
- **Hosts:** All 8 agent workflows
- **Features:** RAG knowledge base (Ariel-Style), workflow builder, API endpoints
- **Status:** LIVE ✅

### GitHub Actions (Automation)
- **Role:** Hands of the production studio
- **Hosts:** Asset generation pipeline, video rendering, deployment
- **Key Workflows:**
  - `asset-generation.yml` — Gemini TTS + Nano Banana images + Pexels B-roll
  - `cc-direct-oauth-fixed.yml` — Claude Code dispatch to Hetzner
  - `deploy-dify-agents.yml` — Dify workflow deployment via SSH

### Supabase (Data Layer)
- **Tables:**
  - `production_briefs` — Creative briefs (BriefAgent output)
  - `production_scripts` — Video scripts (ScriptwriterAgent output)
  - Future: `production_storyboards`, `production_assets`, `production_renders`
- **Storage:** Video assets, rendered MP4s, voiceover files

### Hetzner (Compute)
- **IP:** 87.99.129.125
- **Hosts:** Dify, Claude Code (when auth fixed), Remotion rendering
- **SSH:** Via GHA workflows with HETZNER_SSH_KEY

---

## BACKBONE 8: Existing Video Assets (zonewise-video)

### 7-Scene Composition (180 seconds)
```
Scene 1: Founder's Story     | 30s | 900 frames  | Hero property golden hour
Scene 2: Two Codes Locked    | 25s | 750 frames  | Spreadsheet chaos
Scene 3: Both Codes Cracked  | 15s | 450 frames  | Florida 67-county map
Scene 4: 12-Step Pipeline    | 40s | 1200 frames | Data command center
Scene 5: For Everyone        | 30s | 900 frames  | Persona showcase
Scene 6: The Moat            | 20s | 600 frames  | Patent pyramid
Scene 7: CTA                 | 20s | 600 frames  | SOLD + celebration
```

### 4 Custom Transitions
- FadeWhiteTransition (Scene 1→2)
- CurtainSplitTransition (Scene 2→3)
- ZoomMapTransition (Scene 3→4)
- SlideLeftTransition (Scene 4→5, 5→6, 6→7)

### Generated Assets (in repo)
- `public/audio/voiceover.mp3` — 82s, 777KB, Orus voice (Google TTS)
- `public/audio/voiceover.wav` — 82s, 3.8MB, lossless

---

## WHY WE WIN

### Speed
- Hollywood: 4-12 weeks per 3-minute video
- Us: Same day, same session

### Cost
- Hollywood: $42,000-66,000 per video
- Us: ~$37/month for unlimited production

### Consistency
- Hollywood: Different crew = different style
- Us: DESIGN.md + Ariel-Style RAG = every video matches brand exactly

### Scale
- Hollywood: 1 video at a time
- Us: 67 county spotlight reels generated in batch overnight

### Iteration
- Hollywood: Re-shoots cost $10,000+
- Us: "Regenerate Scene 4 with darker mood" → 30 seconds

### Intelligence
- Hollywood: Creative decisions are human-only
- Us: QAAgent compares every frame against approved briefs + Ariel's style RAG
  Post-Producer AI watches the video and gives scored feedback
  Every approved video trains the system to make the next one better

### Zero Human Bottleneck
- Hollywood: 50+ people coordinating schedules
- Us: 8 AI agents + 1 Creative Director (Ariel) + 1 Executive Producer (Claude)
  3 checkpoints, zero meetings, zero waiting
