# CODE BLUE! — run the ER

A small 3D emergency-department game. Triage the patients, get them into a bed,
run the right test, give the right treatment, don't lose anyone. Solo, or local
two-player co-op on one keyboard.

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
