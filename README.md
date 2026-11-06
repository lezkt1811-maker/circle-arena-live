# 🟣 CIRCLE ARENA LIVE

A neon arena game made for TikTok LIVE-style streams. **The whole game plays on one screen. Nobody steers.**

- Every viewer who comes into the LIVE gets their own glowing circle.
- **The more they tap (like), the bigger their circle grows.**
- **The more gifts they send, the more ⚡ power and abilities they get** to beat the others.
- Circles drift around on their own. Big circles eat smaller ones. Spinning saws cut points off.
- Last circle standing, or the biggest when the 3-minute timer ends, wins the round. Then a new round starts.

The whole game is in **`index.html`**: plain HTML, CSS, and JavaScript with a Canvas. No frameworks, no installs, no paid services, no backend. It works on GitHub Pages and in any modern phone browser.

> **Important:** there is **no real TikTok connection yet.** The 🎁 panel and the 🤖 auto viewers *simulate* LIVE events so you can test and show the game.

---

## 🎮 How it works

| Viewer action | What happens |
|---|---|
| 👋 Joins the LIVE | A new circle with their name appears |
| 👆 Taps / likes | +3 score per tap, and the circle grows |
| 💬 Comments | Joins if they're new, +5, and their message shows in a bubble over their circle |
| ➕ Follows | Joins with +100 and a NEW badge |
| 🎁 Sends a gift | Big score, **⚡ power**, and a special ability (see below) |

**Rules**
- A circle can eat another that is at least **20% smaller**. Similar-size circles bounce off each other.
- ⚙ **Spinning saws** take 8% of a circle's score on each hit. At under 2 points the circle is knocked out.
- A knocked-out viewer comes back as soon as they tap, comment, or gift again.
- The **top 3 wear crowns**. The leaderboard (top-left) shows score and 💀 eats.

### 🎁 Gifts and abilities

| Gift | Score | ⚡ Power | Special ability |
|---|---|---|---|
| 🌹 Rose | +50 | +1 | Speed burst (4s) |
| 💗 Heart | +200 | +3 | Shield bubble (10s): can't be eaten or cut |
| 🌌 Galaxy | +1K | +10 | Shockwave: blasts nearby circles away, and smaller ones lose 15% |
| 🪐 Universe | +5K | +30 | **Hunter mode** (15s): green crosshair, extra speed, chases and eats smaller circles, plus a shield |

**⚡ Power stacks for the whole round.** Every gift adds more, and it shows as a gold ⚡ badge on the circle. Each point of power gives:
- **Speed:** +2% per point, up to +40%.
- **Armor:** saws do less damage.
- **Bump steal:** when two circles bounce, the one with more power steals points from the other.
- **🦈 Giant Jaws at ⚡10:** the circle can eat others that are only 5% smaller, instead of 20%.

So a viewer who taps a lot gets **big**, and a viewer who gifts gets **strong**. Both can win.

---

## 🧪 Testing it yourself

- **Tap anywhere on the screen.** You have a test circle (★ and your name), and each tap is a like for it. On a computer, press **Space**.
- **🤖 Auto viewers** are pretend viewers that join, tap, chat, and gift so the arena feels like a busy LIVE. Turn them on or off in the 🎁 panel.
- **🎁 panel:** send any gift or event yourself. Pick the sender's name and who the gift goes to (the sender's own circle, you, or the leader).
- **❚❚** pauses and **↻** restarts.

---

## 🚀 Put it online with GitHub Pages (free)

1. Open the **circle-arena-live** repository on GitHub. In a phone browser, use the browser menu → **Desktop site** if you can't see Settings.
2. Tap **Settings** → **Pages** (left menu).
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose **main** and **/ (root)**, then tap **Save**.
5. Wait 1–2 minutes and refresh. Your game will be at:
   **`https://lezkt1811-maker.github.io/circle-arena-live/`**

Any change saved to `index.html` on `main` updates the site automatically within a minute or two. If you see an old version, refresh.

To edit on your phone: open the file on GitHub → ✏️ pencil → make the change → **Commit changes**.

## 📱 Using it on your Android phone / on a LIVE

1. Open the GitHub Pages link in **Chrome**.
2. Optional: tap **⋮ → Add to Home screen** so it opens full-screen like an app.
3. Type a name and tap **START**.
4. To show it on a LIVE today, you'd share your screen or point a second phone or camera at it. Viewer taps and gifts on TikTok won't reach the game until a real connection is built (see below).

**Easy tweaks:** near the top of the script in `index.html`, the `CONFIG` section has the round length (`ROUND_TIME`), points per tap (`TAP_SCORE`), number of saws (`SAW_COUNT`), and more. Gift values are in `GIFTS`.

---

## 🔌 Future: connecting real TikTok LIVE events

The game listens for events in one place (`LiveEvents`). The simulator buttons and auto viewers already send events in the exact format a real connection would use:

```js
{ "type": "like",    "user": "name", "count": 15 }
{ "type": "join",    "user": "name" }
{ "type": "follow",  "user": "name" }
{ "type": "comment", "user": "name", "comment": "hi!" }
{ "type": "gift",    "user": "name", "gift": "rose" }   // rose | heart | galaxy | universe
```

TikTok doesn't offer a free, official browser API for LIVE events. Connecting them would need a small relay server that you run and that complies with TikTok's terms. The relay would forward events as JSON to `CircleArena.LiveEvents.connectBridge("wss://your-relay")`, which is already in the code. Gameplay wouldn't need to change. More TikTok gift names can be added to `GIFTS`.

## 🌐 Future: Cloudflare Workers

A Cloudflare Worker (with a Durable Object) could be that relay. It would receive LIVE events, run one shared arena, and send the same game to every screen watching. That way a viewer could open the link and watch their own circle live. The game logic is kept separate from the drawing code so it can move to a server later. None of this is needed for the current version.

---

Original design and code. HTML5 Canvas + vanilla JavaScript.
