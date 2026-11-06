# 🟣 CIRCLE ARENA LIVE

A neon arcade arena game for phone and computer. Collect glowing energy pellets, grow bigger, eat smaller circles, and don't get eaten.

- **Simple files:** `index.html` (LIVE Arena) and `classic.html` (joystick mode). It uses HTML, CSS, and plain JavaScript with a Canvas.
- **Nothing to install:** no frameworks, no build tools, no paid services, no backend.
- **Works on GitHub Pages** and in any modern phone browser.
- **14 computer players** (AI) keep the arena busy even when you're alone.
- **LIVE event simulator (🎁 button):** test TikTok-style gifts, likes, follows, joins, and comments. These are *simulated*. There is **no real TikTok connection yet.**

---

## 🎮 Two modes

| File | Mode |
|---|---|
| `index.html` | **LIVE Arena (main game).** The whole arena fits on one screen. Every circle is a viewer. **Taps (likes) grow your circle**, gifts power it up, big circles eat small ones, and spinning saws cut you down. Last circle standing, or the biggest when the 3-minute timer ends, wins the round. |
| `classic.html` | **Classic.** Steer your own circle around a big scrolling arena with a joystick. |

### LIVE Arena: how to play
- Tap **START**. Your circle has a ★ and your name.
- **Tap anywhere on the screen** as fast as you can. Every tap is a like and makes your circle bigger. (On a computer, press Space.)
- Circles drift around on their own. A circle can eat another that's at least 20% smaller.
- ⚙ **Spinning saws** take 8% of a circle's score on each hit.
- Top 3 wear **crowns**. The leaderboard (top-left) shows score and 💀 eats.
- **🤖 Auto viewers** (in the 🎁 panel) are pretend viewers who join, tap, comment, and send gifts so the arena is busy. Turn them off to test by hand.
- Gifts: 🌹 Rose +50 & speed · 💗 Heart +200 & shield · 🌌 Galaxy +1K & shockwave · 🪐 Universe +5K & **hunter mode** (green crosshair, chases and eats smaller circles) · ➕ Follow joins with +100 · 💬 Comment joins and shows a chat bubble.

---

## 🎮 Classic mode: how to play

| | Phone | Computer |
|---|---|---|
| Move | Put your thumb anywhere on the **left side** of the screen and drag (joystick) | Move the **mouse**, or use **WASD / arrow keys** |
| Boost | Hold the pink **BOOST** button (bottom-right) | Hold **Space** (or **Shift**, or the left mouse button) |
| Pause | ❚❚ button | ❚❚ button, **P**, or **Esc** |
| Restart | ↻ button | ↻ button |
| LIVE simulator | 🎁 button | 🎁 button |

**Rules**
- Eat pellets to grow. Your **Score** goes up with everything you collect.
- You can only eat a player who is **at least 15% smaller** than you. Equal-size players bump off each other.
- Boosting makes you faster but burns a little of your size.
- New players get a short **🛡 shield** after spawning.
- Bigger players move slower and shrink slowly once they're very large.
- When you're eaten, tap **RESPAWN** to jump back in.

---

## 🎁 LIVE event simulator (development tool)

Open it with the 🎁 button. Choose a **Sender** (or leave it blank for a random viewer name) and a **Target** (You / Leader / Random / Smallest).

| Button | What happens in the game |
|---|---|
| 🌹 Rose | Target gets +15 energy |
| 💗 Heart | Target gets a 6-second speed boost |
| 🌌 Galaxy | Energy explosion: 70 big pellets fly out and nearby players get pushed away |
| 🪐 Universe | Transformation: big growth, rainbow aura, 12 seconds of shield and extra speed |
| ➕ New Follower | A new AI player named after the follower enters the arena near you |
| 👍 Likes ×10 | Fills the Community meter. At 100% an **Energy Storm** happens (pellet storm, everyone +8) |
| 👋 Viewer Joins | Viewer count goes up and an energy drop appears near you |
| 💬 Special Comment | Type a comment containing `rain`, `gold`, `shrink`, or `magnet` for that event. Any other comment picks one at random |

Comment events: **rain** = pellet rain · **gold** = Golden Hour, pellets are worth double for 15s · **shrink** = the leader loses 35% of their size · **magnet** = the target pulls in nearby pellets for 10s.

---

## 🚀 Put it online with GitHub Pages (free)

Your files are already in the GitHub repository **circle-arena-live**. To turn on the website:

1. Open the repository on GitHub, in your phone browser or the GitHub app. If the app doesn't show Settings, use the browser and tap **"Desktop site"** in the browser menu.
2. Tap **Settings** (the ⚙ tab at the top of the repo).
3. In the left menu, tap **Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Under **Branch**, choose **main**, set the folder to **/ (root)**, and tap **Save**.
6. Wait 1–2 minutes, then refresh the page. A link appears at the top:
   **`https://lezkt1811-maker.github.io/circle-arena-live/`**
7. Open that link to play. Share it with anyone.

### Updating the game later
Any change you save to `index.html` on the `main` branch updates the website automatically, usually within a minute or two. If you still see the old version, refresh the page or close and reopen the tab.

To edit a file on your phone: open the file on GitHub → tap the ✏️ pencil → make the change → tap **Commit changes**.

---

## 📱 Testing on your Android phone

1. Open the GitHub Pages link in **Chrome**.
2. Turn the phone sideways (landscape) or keep it upright. Both work.
3. Type a username and tap **PLAY**.
4. Put your left thumb on the left half of the screen and drag to steer. The joystick appears where you touch.
5. Hold **BOOST** with your right thumb to dash.
6. Tap 🎁 and try each gift button. You should see an effect in the arena and a message near the bottom of the screen.
7. Tap ❚❚ to pause and ↻ to restart.

**Tip: make it feel like an app.** In Chrome, tap the **⋮** menu → **Add to Home screen**. It gets its own icon and opens full-screen.

**If something seems wrong:**
- Old version showing → pull down to refresh, or close the tab and reopen it.
- Screen moves or zooms → make sure you opened the real link, not a preview inside another app.
- Game feels slow → close other tabs. The game limits its own detail level on high-resolution screens.

### Testing without publishing
Download `index.html` to your phone, then open it from Chrome by typing `file:///sdcard/Download/index.html` in the address bar. (On some phones Chrome blocks this. If it does, use the GitHub Pages link.)

---

## 🧱 How the code is organized

Everything is inside the `<script>` in `index.html`, split into clear sections:

| Section | Job |
|---|---|
| `CONFIG` | All tuning numbers in one place: arena size, speeds, bot count, eat ratio, boost cost… |
| `Sim` | **Pure game logic.** Movement, pellets, eating, collisions, respawning, gift effects. No drawing and no screen code. |
| `AI` | Computer opponents. They run from bigger players, chase smaller ones, collect pellets, and avoid walls. |
| `LiveEvents` | A small event bus. The 🎁 panel sends events into it, and the game listens. |
| `Input` | Joystick, boost button, mouse, and keyboard. |
| `Renderer` | Draws everything on the canvas: glow, particles, minimap, camera. |
| `UI` | HUD, leaderboard, menus, and messages. |
| `Game` | The main loop that connects everything. |

**Easy tweaks:** change values in `CONFIG` near the top of the script. For example, `BOT_COUNT: 14` controls how many computer players there are, and `WORLD_W` / `WORLD_H` control the arena size.

**Debugging:** on a computer, open the browser console (F12) and use `CircleArena.Game.world`, or send a test event:
```js
CircleArena.LiveEvents.emit({ type: 'gift', gift: 'galaxy', user: '@tester', target: 'me' })
```

---

## 🔌 Future: real TikTok LIVE events

The game is ready for real events, but **it is not connected to TikTok today.** TikTok does not offer an official, free browser API for LIVE gifts. A real connection would need a small relay server that you run and that complies with TikTok's terms. That relay would forward events to the game as JSON in this shape:

```js
{ "type": "gift",    "gift": "rose", "user": "@name", "target": "leader" }
{ "type": "follow",  "user": "@name" }
{ "type": "like",    "user": "@name", "count": 15 }
{ "type": "join",    "user": "@name" }
{ "type": "comment", "user": "@name", "comment": "make it rain" }
```

The game already contains `CircleArena.LiveEvents.connectBridge("wss://your-relay.example")`. It connects to any WebSocket that sends messages in that format and feeds them into the same handler the 🎁 buttons use. Gameplay code wouldn't change. To map more TikTok gift names to effects, edit the `gift` cases inside `applyLiveEvent`.

---

## 🌐 Future: real multiplayer with Cloudflare Workers

This version runs completely in your browser. It was built so it can later become real online multiplayer:

- `Sim` has **no screen code**, so the same logic can run on a server.
- Every player, human or bot, is controlled only through `Sim.setInput(player, dx, dy, boost)`. The server would do exactly this with inputs it receives.
- The game advances in fixed 1/60-second steps (`Sim.step(world, dt)`), so a server can run the same timing.
- Things the screen should react to (eats, level-ups, explosions) go into `world.events` and are not drawn directly. A server can send these to clients.

**Suggested plan (free Cloudflare tier):**

1. **Cloudflare Worker + one Durable Object per arena room.** The Durable Object holds the `world` and runs `Sim.step` about 30 times per second. It is the "referee," so nobody can cheat by editing their own browser.
2. **Players connect with a WebSocket** to `wss://your-worker.workers.dev/room/main`.
3. **Browser → server** (about 20 times per second): only the controls.
   `{ "t": "input", "dx": 0.7, "dy": -0.2, "boost": false }`
   plus `{ "t": "join", "name": "Katy" }` once at the start.
4. **Server → browsers** (10–20 times per second): a small snapshot of nearby players and pellets, plus that tick's events.
   `{ "t": "snap", "time": 123.4, "you": 7, "players": [[id, x, y, mass, colorIndex, name], ...], "events": [...] }`
5. **The browser** stops running `Sim.step` itself and smoothly slides each circle toward its latest server position (interpolation). `Renderer` and `UI` stay almost unchanged.
6. **Gifts** from a LIVE relay would go to the server, so every player sees the same Galaxy explosion at the same moment.

None of this is needed for the current version. It works on GitHub Pages as-is.

---

Made with HTML5 Canvas + vanilla JavaScript. Original design and code.
