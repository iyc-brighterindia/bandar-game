# BanDar! — Final gameplay patch (road additions) — test report

Only three additions; everything else is unchanged (story, dialogue, audio, opening, finale, certificate, QR, sharing, screens).

1. **Right-wing goon obstacle (`GOON`)** — from the supplied artwork (`assets/obs_goon.webp`, original in `assets/source/`). He stands in one lane with his stop gesture and lathi, shuffling side to side and bobbing. Dodge by changing lane (jumping or sliding doesn't work).
2. **Police + barricade obstacle (`POLICE`)** — one combined hurdle from the supplied artwork. The smoky backdrop was removed by tracing the artwork's outline (`assets/obs_police.webp`). It has a subtle stop-gesture bob and appears in different lanes in all four worlds, most often at Checkpoint Row. Dodge by changing lane.
3. **Collectible posts** — the existing collectible post is placed in free lanes between obstacle rows: 1 per row, sometimes 2. Measured **16–20 per run**; a steering player collected 11. The four curated post moments are unchanged.

Both new obstacles reuse the existing obstacle system (`B.OBS`, row generator, fairness check, collisions, hit effects). The road still always leaves a free path, and each row still comes every 1.7–1.8 s.

## Measured (real time, offline, exported dist/index.html)
| | 390×844 | 1280×800 |
|---|---|---|
| CHALLENGE pressed → certificate | **56.57 s** | **56.58 s** |
| Page shown → certificate | 58.0 s | 57.78 s |
| Gameplay section | 24.5 s | 24.5 s |

Approved build for comparison: CHALLENGE → certificate 56.6 s (390×844). **No time added**; the gameplay section is still exactly 24.5 s. The small difference in total time comes from page load and name entry (bundle +118 KB for the two sprites).

Voice order unchanged: 01 → 05 → 07 → 10 → 12 → 13 → 20 → 16 → 17 → 18 → 21 → 19.

Regression: certificate auto-appears (CHALLENGED BY MANU), 1080×1350 / 1200×675 / 1080×1920 PNGs with the QR decoding to https://www.iyc.in/bandar, Copy Link / Challenge a Friend / share message / simulated native file share OK, Godi pop-up synced to clip 10, 21/21 voices, 8/8 unit tests, 0 console errors (mobile and desktop).
