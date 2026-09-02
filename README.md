# AR Experience — Deploy to GitHub Pages

## Folder structure
```
ar-experience/
├── index.html
└── assets/
    ├── marker.patt       # your working pattern file — has real data, verified
    └── asset.gif         # the AR overlay content
```

Note: this package doesn't include a marker image — use whichever printed/displayed
marker you already have working with this `marker.patt`. If you don't have it handy
anymore, let me know and we'll regenerate it from this same `.patt` reference so they
stay in sync.

## Deploy steps

1. **Create (or reuse) a GitHub repo**, public.
2. **Upload the contents of this folder** so `index.html` sits at the repo root and
   `assets/` is a subfolder right next to it — not nested inside another folder.
3. **Enable GitHub Pages**: repo → Settings → Pages → Source: `Deploy from a branch`,
   branch `main`, folder `/ (root)` → Save.
4. Open `https://<your-username>.github.io/<repo-name>/` on your phone, allow camera
   access, and point it at your marker.

## Using it

- The GIF floats above the marker, gently bobbing up and down, and spins continuously
  on its own.
- **Drag with one finger** anywhere on screen to manually rotate it — auto-spin pauses
  while you're dragging and picks back up right where it left off once you let go.
- **Pinch with two fingers** to scale it up or down (clamped between 0.4x and 2.5x).

This interaction is handled by a small custom `float-interact` script inside
`index.html` (no external gesture library needed), so there's nothing extra to upload.

## If detection stops working again

- Re-verify `assets/marker.patt` isn't all zeros before deploying — a quick way to
  check: open it in a text editor and confirm you see numbers other than 0 scattered
  throughout, not a uniform block of zeros.
- Keep using the same marker image that was generated alongside this specific
  `marker.patt` — mixing and matching pattern files with unrelated marker images is
  the other common cause of "nothing scans."
