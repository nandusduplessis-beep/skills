# CLAUDE.md

## Project Overview

This is `@remotion/skills` — an internal knowledge-base package containing best practices and documentation for [Remotion](https://www.remotion.dev/), the React-based video creation framework. It is part of the `remotion-dev/remotion` monorepo (under `packages/skills`).

The package serves as a skill reference for AI assistants working with Remotion projects, providing markdown rules, code examples, and executable demo compositions.

## Repository Structure

```
skills/
├── package.json          # Private package, v4.0.429
├── tsconfig.json         # TypeScript config (noEmit, react-jsx)
├── README.md             # Internal-use notice
├── src/
│   ├── index.ts          # Entry point — registers RemotionRoot
│   └── Root.tsx          # Demo compositions (BarChart, Typewriter, WordHighlight)
└── skills/remotion/
    ├── SKILL.md           # Skill metadata and index
    └── rules/
        ├── *.md           # 43 rule files (best-practice documentation)
        └── assets/        # Example TSX components referenced by rules
            ├── charts-bar-chart.tsx
            ├── text-animations-typewriter.tsx
            └── text-animations-word-highlight.tsx
```

## Commands

- **`npm run dev`** — Starts Remotion Studio for previewing demo compositions

No test suite or build step exists; this is a documentation-only package (`noEmit: true`).

## Key Conventions

### File Naming
- Rule files: **kebab-case** (e.g., `text-animations.md`, `get-video-duration.md`)
- React components: **PascalCase** (e.g., `MyAnimation`)
- Composition IDs: **PascalCase** (e.g., `BarChart`, `Typewriter`)

### Rule File Format
Each rule file uses YAML frontmatter with `name`, `description`, and `metadata.tags`, followed by markdown content with code examples and links to related rules.

### Remotion Code Patterns
- Use `useCurrentFrame()` and `useVideoConfig()` for animation — CSS transitions and `requestAnimationFrame` are forbidden
- Use `spring()` or `interpolate()` for all motion/timing
- Use `staticFile()` to reference assets from the `public/` folder
- Use `@remotion/google-fonts` for font loading
- Compositions require: `id`, `component`, `width`, `height`, `fps`, `durationInFrames`

### Rule Categories (43 rules in `skills/remotion/rules/`)
| Category | Topics |
|---|---|
| Animation & Motion | animations, text-animations, timing, transitions, sequencing, trimming, light-leaks |
| Media & Assets | assets, videos, audio, images, gifs, fonts, get-audio-duration |
| Data & Visualization | charts, 3d, lottie, measuring-text, measuring-dom-nodes, maps |
| Audio & Effects | audio-visualization, sfx, voiceover, extract-frames, can-decode |
| Video Processing | get-video-dimensions, get-video-duration, transparent-videos, ffmpeg |
| Captions & Text | subtitles, display-captions, transcribe-captions, import-srt-captions |
| Structure & Config | compositions, parameters, calculate-metadata |
| Styling | tailwind |

## Dependencies

Core Remotion packages: `remotion`, `@remotion/bundler`, `@remotion/cli`, `@remotion/media`, `@remotion/shapes`, `@remotion/three`, `@remotion/lottie`, `@remotion/google-fonts`. Also uses React 19, ESLint, and TypeScript (native preview).

External integrations documented in rules: Mediabunny (media analysis), ElevenLabs (TTS), Mapbox (maps), FFmpeg (video processing).

## Working with This Repo

- **Adding a new rule:** Create a kebab-case `.md` file in `skills/remotion/rules/` with proper YAML frontmatter (`name`, `description`, `metadata.tags`). Include code examples and link to related rules.
- **Adding a demo component:** Place `.tsx` files in `skills/remotion/rules/assets/` and register a `<Composition>` in `src/Root.tsx`.
- **This is a private, internal package** — no publishing, no public docs.
