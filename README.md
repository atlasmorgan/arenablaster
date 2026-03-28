# Arena Blaster

A retro-style top-down arcade shooter built with vanilla JavaScript, HTML Canvas, and Tailwind CSS. Defend the arena against waves of alien ships, rack up points, and compete on the global leaderboard powered by Firebase.

---

## How to Play

### Objective
Survive as long as possible, shoot down enemy ships, and don't let them reach you — or the bottom of the screen.

### Controls

| Action | Keyboard | Mobile / Tablet |
|---|---|---|
| Move | WASD or Arrow Keys | On-screen D-pad |
| Shoot | Space | FIRE button |
| Restart | Play Again button | Play Again button |

### Scoring & Lives
- You start with **3 lives**
- **+1 point** for every enemy ship you destroy
- **−1 life** if an enemy ship touches you
- **−1 life** if an enemy bullet hits you
- **−1 life** if an enemy ship reaches the bottom of the screen
- **0 lives = Game Over** — your score is automatically saved to the leaderboard

---

## Running Locally

No server, no install, no build step required.

1. Clone or download this repo
2. Open `index.html` in any modern browser (Chrome, Firefox, Safari, Edge)

That's it. The game runs entirely in the browser.

```bash
git clone https://github.com/atlasmorgan/arenablaster.git
cd arenablaster
open index.html   # macOS
# or just double-click index.html in Finder / Explorer
```

---

## Firebase Leaderboard

The global leaderboard is powered by [Firebase Firestore](https://firebase.google.com/docs/firestore).

- Scores are stored in a `scores` collection with `name`, `score`, and `timestamp` fields
- The top 10 scores are fetched and displayed on the Game Over screen after each game
- Your name is entered once at the start and reused for every run

> **Note on the API key:** Firebase web API keys are intentionally public — they simply identify the Firebase project. Security is enforced through [Firestore security rules](https://firebase.google.com/docs/firestore/security/get-started), not by keeping the key secret. This is standard practice for all Firebase web apps.

---

## Project Structure

```
arena blaster/
├── index.html       # The entire game — HTML, CSS, and JS in one file
├── assets/
│   ├── bgmusic.mp3      # Background music (loops during play)
│   ├── shoot.mp3        # Player shoot sound
│   ├── hit.mp3          # Lose-a-life sound
│   └── gameover.wav     # Game over sound
└── README.md
```

---

## Tech Stack

- **HTML Canvas** — all game rendering
- **Vanilla JavaScript** — game loop, physics, collision detection
- **Tailwind CSS** (CDN) — HUD and UI styling
- **Firebase Firestore** (CDN) — leaderboard persistence
