# Tsuki — setup notes

## 1. Fonts (do this first — currently falling back to system fonts)
I couldn't download font files in this environment (no network access), so the
site currently falls back to system serif/sans-serif fonts. To get the real
look, download these two free Google Fonts and drop the `.woff2` files into
`assets/fonts/` with these exact names:

- `assets/fonts/ShipporiMincho-Regular.woff2` — from Shippori Mincho (weight 400)
- `assets/fonts/ShipporiMincho-Bold.woff2` — from Shippori Mincho (weight 700)
- `assets/fonts/ZenKakuGothicNew-Regular.woff2` — from Zen Kaku Gothic New (weight 400)
- `assets/fonts/ZenKakuGothicNew-Medium.woff2` — from Zen Kaku Gothic New (weight 500)

Get them at fonts.google.com (search each name → "Get font" → convert the
.ttf to .woff2 with a free converter like cloudconvert.com, or use
google-webfonts-helper.herokuapp.com which gives you woff2 directly).

## 2. Image resolution — important
Your uploaded images are **1376×768** and the video is **1280×720** — not the
4K UHD the brief asked for. I used them at full quality with no upscaling
(upscaling would make them softer, not sharper). If you want true 4K, re-export
or re-generate the source images at higher resolution and swap the files in
`assets/` — the filenames can stay the same and everything else will just work.

## 3. What's placeholder and needs your input
- **Chapter 03 (Tsukuri)** — your 3 projects are in (Anime Store, Birthday Wish, JJK Domain
  Expansion). Two things to finish yourself:
  - Each "View on GitHub" button currently points at your GitHub *profile*
    (github.com/Pandu32180), not the specific repo — swap each `href` in
    `index.html` for the actual project repo URL.
  - Each thumbnail is a colored placeholder, not a real screenshot — replace
    the `.proj-thumb` div's background with an `<img>` of your actual project
    (a browser screenshot works well) once you have one for each.
- **Chapter 04 (Takumi)** skill tags are a guess based on "AI-assisted web development" —
  edit the `.tag-row` in `index.html` to match what you actually know.

## 4. Deploying to GitHub Pages
This is a single static site with only relative paths — no build step needed.
1. Push this whole folder (`index.html`, `assets/`) to a GitHub repo.
2. In the repo settings → Pages → set source to the main branch, root folder.
3. Done — no `npm install`, no bundler.

## 5. Before you call it done
Open the deployed (or local) site and check, per the original brief:
- Desktop width and ~390×844 (a phone-sized viewport)
- Browser console for errors (right-click → Inspect → Console)
- Every nav link scrolls to the right chapter
- The hero video actually autoplays (some mobile browsers block autoplay
  even when muted — if so, the poster image `ch1-poster.png` will show instead,
  which is expected fallback behavior, not a bug)
