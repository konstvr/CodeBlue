# CODE BLUE! — run the ER

A small 3D emergency-department game. Triage the patients, get them into a bed,
run the right test, give the right treatment, don't lose anyone. Solo, or local
two-player co-op on one keyboard.

**▶ Play: `https://<your-username>.github.io/<repo>/`**

Made for Βράδια Έρευνας / Researchers' Night 2026 at the University of Crete.

---

## Modes

- **🍿 Night Shift** — casual. Match the symbols, treat the patients, survive
  the rush. No medical knowledge needed.
- **🩺 Attending** — for medical students. Real cases: read the vignette,
  choose the right test and treatment while the clock runs.

## Difficulty

Changes how many patients arrive, how fast their vitals fall, and what each
case pays:

| | patients (solo, day 1 → 5) | a red patient survives | pay, green / red |
|---|---|---|---|
| 🩹 **Quiet Night** | 4.5 → 9.4 | 44s | $9 / $21 |
| 🚑 **Busy Night** | 5.3 → 11.1 | 34s | $7 / $17 |
| 💀 **Code Black** | 6.4 → 13.5 | 26s | $5 / $13 |

In co-op the department gets ~28% busier to match having two doctors, so a
tier means the same thing alone or with a friend.

---

## Controls

### 1 player

| | |
|---|---|
| Move | WASD or Arrow keys |
| Pick up / put down / into bed | **Left click** |
| Triage, treat, change linens | **Hold right click**, or hold **E** |
| Drop what you're carrying | **Q** |
| Answer (Attending mode) | **1–4** |
| Mute / pause | **M** / **Esc** |
| Scenery on/off (if it runs slowly) | **G** |

### 2 players — one keyboard

| | Player 1 | Player 2 |
|---|---|---|
| Move | **W A S D** | **Arrow keys** |
| Interact | **E** | **Right Shift** (also Enter, Numpad 0, Right Ctrl) |
| Drop | **Q** | **Delete** (also Numpad 1) |

Both players share one department, one wallet and one set of lives — they're
helping each other, not competing. P1 wears a blue ring, P2 an amber one.

---

## Publishing it

**One file: `index.html`.** three.js is bundled inside it — no images, no
stylesheets, no build step, no dependencies. It makes zero external network
requests unless you switch on analytics below.

1. Create a public GitHub repository.
2. Upload `index.html` (and this `README.md`).
3. **Settings → Pages** → Source: *Deploy from a branch*, branch `main`,
   folder `/ (root)` → Save.
4. About a minute later it's live at
   `https://<your-username>.github.io/<repo>/`

Because it's one self-contained file, it works just as well emailed, put on a
USB stick, or opened from disk with no connection at all.

---

## Analytics (optional, off by default)

Find this line near the top of `index.html`:

```js
var GOATCOUNTER_CODE = '';
```

Put your [GoatCounter](https://www.goatcounter.com) code between the quotes
(from your dashboard URL, `https://MY-CODE.goatcounter.com`). Leave it empty
and nothing loads at all — no script, no request.

**Why GoatCounter:** no cookies, and nothing written to the visitor's browser.
Sessions are a salted hash of IP + User-Agent held in memory for 8 hours and
never stored; IP addresses aren't kept. In practice that means no consent
banner. Free for non-commercial use, and it supports custom events.

Beyond pageviews, the game reports these anonymous aggregate events:

| event | tells you |
|---|---|
| `start/<mode>/<players>p/<difficulty>` | which setup people pick |
| `character/<species>` | which animal is most popular |
| `gameover/<difficulty>/day-<n>` | how far people get — the key tuning number |
| `treated/<bucket>` | patients treated per run |
| `feedback/rating/<1-5>` | star ratings in aggregate |
| `feedback/who/<pupil\|student\|parent\|health-pro\|other>` | who's playing |
| `feedback/with-comment` | that a comment was left, not what it said |

Two deliberate limits:

- **Free-text comments are never sent.** They're the visitor's own words.
- **Nothing loads from a `file://` page**, even with a code set, so a
  downloaded copy stays completely offline.

An explicit Do Not Track signal also disables it.

---

## Feedback

Players can leave a star rating, say who they are, and write a comment — from
the home screen or after a run.

**It is stored in that visitor's own browser and sent nowhere.** Star ratings
and the audience breakdown reach you through analytics; **the written comments
do not.** Each visitor's text stays on their machine.

To read what's stored on any one machine, press **Ctrl+Shift+F** there. The
panel shows the count and average rating and offers **⬇ Download
feedback.json** or **📋 Copy JSON** — handy for testers you can ask directly.

Stored shape:

```json
[
  {
    "ts": "2026-09-25T18:42:11.950Z",
    "rating": 4,
    "who": "Φοιτητής/τρια",
    "whoId": "student",
    "text": "Πολύ ωραίο! More beds please.",
    "mode": "casual",
    "players": 2,
    "difficulty": "busy",
    "outfits": ["bear", "frog"],
    "bestDay": 3,
    "treated": 11
  }
]
```

---

## Credits

Game and 3D art hand-built with [three.js](https://threejs.org) r150 (MIT),
bundled inline. Made for Βράδια Έρευνας 2026 · STEPS · University of Crete.
