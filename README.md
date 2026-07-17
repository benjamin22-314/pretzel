# 🥨 Pretzel Party

A pretzel-making game for Amy! Mix the dough, shape it, decorate it, bake it, and eat it.

**Live app:** https://benjamin22-314.github.io/pretzel/

## Features

- **Mix the dough** — tap each (vegan!) ingredient into the bowl: flour, warm water, yeast, maple syrup, salt, and oil — then tap the bowl to stir it up.
- **Pick a shape** — classic pretzel, heart, star, ring, worm, an **A for Amy**, or draw your very own shape with a finger.
- **Decorate** — sprinkle on salt, rainbow sprinkles, (vegan) chocolate drizzle, cinnamon, sesame seeds, or googly eyes. Toppings only stick to the dough!
- **Bake** — watch it turn golden in the oven window, with a ding and confetti when it's done.
- **Eat** — tap to take crunchy bites until it's all gone.
- **Photo gallery** — every pretzel is saved as a photo (auto-saved before eating, too). View, download, or delete them.
- Silly synth sound effects (toggleable), a baked-pretzel counter, and big kid-friendly buttons.

## Tech notes

- Zero-dependency PWA: a single `index.html` with inline CSS/JS — no build step, frameworks, fonts, or CDNs. Works fully offline.
- Installable: `manifest.webmanifest` + service worker + PNG icons (192/512/maskable/apple-touch). "Add to phone" button triggers `beforeinstallprompt` on Android/desktop and shows Share → Add to Home Screen steps on iOS.
- All paths are relative (`./`) so it works from the GitHub Pages subpath.
- Service worker precaches the app shell, serves cache-first with background refresh, and uses a versioned cache name (`pretzel-v1`) — **bump it on every change** so installed phones pick up updates.
- Photos are stored on-device in IndexedDB (JPEG blobs rendered from the canvas); `navigator.storage.persist()` is requested on boot. No accounts, no backend — data is per-device and lost if the app is uninstalled.
- Sounds are synthesized with WebAudio (no audio files).
- Icons generated with a PowerShell System.Drawing script (a trefoil-knot curve, which happens to look exactly like a pretzel).
