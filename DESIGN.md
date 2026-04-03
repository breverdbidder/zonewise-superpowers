# ZoneWise.AI — Brand Design Specification

Use this file to maintain brand consistency across all generated designs, images, and videos.

## Colors
| Role | Hex | Usage |
|------|-----|-------|
| Primary | #1E3A5F | Navy — headers, primary text, backgrounds |
| Accent/CTA | #F59E0B | Orange — buttons, highlights, call-to-action |
| Background | #020617 | Slate 950 — dark mode base |
| Surface | #0F172A | Slate 900 — card backgrounds |
| Text Primary | #FFFFFF | White on dark backgrounds |
| Text Secondary | #94A3B8 | Slate 400 — secondary text |
| Success/BID | #22C55E | Green — positive actions |
| Warning/REVIEW | #F59E0B | Yellow — caution actions |
| Danger/SKIP | #EF4444 | Red — negative actions |

## Typography
| Element | Font | Weight | Size (video) |
|---------|------|--------|-------------|
| H1 / Hero | Inter | Bold (700) | 96-120px |
| H2 / Scene Title | Inter | SemiBold (600) | 72-84px |
| Body / Description | Inter | Regular (400) | 36-48px |
| Caption / Subtitle | Inter | SemiBold (600) | 48px, white with 2px black outline |
| Data / KPI | Inter | Bold (700) | 84-120px |
| Label | Inter | Medium (500) | 24-32px |

## Logo
- Text mark: "ZoneWise.AI"
- "Zone" in Navy #1E3A5F
- "Wise" in Orange #F59E0B
- ".AI" in Navy #1E3A5F
- Font: Inter Bold

## Video Specifications
| Property | Value |
|----------|-------|
| Resolution (landscape) | 1920x1080 (16:9) |
| Resolution (portrait) | 1080x1920 (9:16) |
| Resolution (square) | 1080x1080 (1:1) |
| Frame rate | 30 fps |
| Codec | H.264 |
| Quality | CRF 18 |
| Background | #020617 with subtle MeshGradient animation |
| Transitions | Spring physics, 15-30 frames (0.5-1s) |

## Image Generation Prompts (Nano Banana Pro)
Always include these modifiers:
- "professional real estate photography"
- "Florida architecture, palm trees, warm lighting"
- "navy blue (#1E3A5F) and orange (#F59E0B) accent colors"
- "clean, modern, minimal UI design"
- "4K resolution, sharp focus"

## Mapbox Style
- Base: mapbox://styles/mapbox/dark-v11
- County fills: Navy #1E3A5F at 0.6 opacity
- Active county: Orange #F59E0B at 0.8 opacity
- Labels: Inter Bold, white with black halo
- Token: Available as MAPBOX_TOKEN in GitHub secrets
