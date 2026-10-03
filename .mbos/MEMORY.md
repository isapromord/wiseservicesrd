# MEMORY - Compound Wisdom & Retrospective Log

### [2026-10-03] Wise Services RD - Setup, 403 Diagnostics & Video Hero Integration
- **Root Cause Analysis (403 Forbidden):**
  - Origin domain `wiseservicesrd.com` resolved to `ns1.dns-parking.com` because Hostinger hosting plan expired on 2026-10-20. The server blocked traffic with HTTP 403.
  - Solution: Extracted the Stitch project, initialized a clean git repository under `isapromord/wiseservicesrd`, and deployed immediately to GitHub Pages (`https://isapromord.github.io/wiseservicesrd/`).
- **Material Symbols Ligature Rendering Bug:**
  - Tailwind CDN + Google Fonts icon tags rendered text literals (e.g. "trending_up") instead of vector glyphs.
  - Fix: Added CSS rule with `-webkit-font-feature-settings: 'liga'; font-feature-settings: 'liga';` and explicit font-family fallback.
- **Tailwind Stacking Context with Video Backgrounds:**
  - Using `-z-20` on a video container causes it to be occluded by `<main class="bg-surface">` background color.
  - Solution: Keep video at `z-0`, gradient overlays at `z-[1] pointer-events-none`, and content at `z-10`.
- **Faststart Streaming for Web Video Delivery:**
  - Large MP4 video files (~25MB) downloaded from Google Drive stall browsers unless the `moov` atom is placed at the front.
  - Optimization: Ran `ffmpeg` with `-movflags +faststart -crf 24 -an` producing a 6.4MB 1080p stream and a 2.8MB 720p fallback, enabling instant autoplay.
