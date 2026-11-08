# Tacoma Narrows 3D video (Three.js + Remotion)

## Setup (once, Node 18+)
    ./setup.sh

## Preview
    npm run dev
Ships with SILENT placeholder narration and estimated caption timings, so the whole
animation plays immediately.

## Real voiceover
1. Put your key in `.env` (copy `.env.example`).
2. `npm run voice` writes `public/voiceover.mp3` and word-exact `public/captions.json`.
   Every 3D beat (cut, collapse on the word "tore") re-syncs automatically.

## Render
    npm run render        # 1080x1920 vertical -> out/tacoma-vertical.mp4
    npm run render:wide   # 1920x1080

## Edit
- Narration: `script.json` (then re-run `npm run voice`). Keep the 5 sections.
- Bridge physics/timing: `src/bridge.ts`. Cameras and set: `src/Scene3D.tsx`.
- Timeline mapping: `src/timeline.ts`. Captions: `src/Captions.tsx`.
- GPU-less server: set `swangle` in remotion.config.ts.
