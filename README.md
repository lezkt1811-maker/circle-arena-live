# 🟣 CIRCLE ARENA LIVE

A neon arena game made for TikTok LIVE-style streams. **The whole game plays on one screen. Nobody steers.**

- Every viewer who comes into the LIVE gets their own glowing circle.
- **The more they tap (like), the bigger their circle grows.**
- **The more gifts they send, the more ⚡ power and abilities they get** to beat the others.
- Circles drift around on their own. Big circles eat smaller ones. Spinning saws cut points off.
- Last circle standing, or the biggest when the 3-minute timer ends, wins the round. Then a new round starts.

The whole game is in **`index.html`**: plain HTML, CSS, and JavaScript with a Canvas. No frameworks, no installs, no paid services, no backend. It works on GitHub Pages and in any modern phone browser.

> The 🎁 panel and 🤖 auto viewers **simulate** LIVE events for testing. For a real LIVE, connect through TikFinity. See **Going LIVE for real** below.

---

## 🎮 How it works

| Viewer action | What happens |
|---|---|
| 👋 Joins the LIVE | A new circle with their name appears |
| 👆 Taps / likes | +3 score per tap, and the circle grows |
| 💬 Comments | Joins if they're new, +5, and their message shows in a bubble over their circle |
| ➕ Follows | Joins with +100 and a NEW badge |
| 🎁 Sends a gift | **50 points per coin**, ⚡ power, and special powers (see below) |

**Rules**
- A circle can eat another that is at least **20% smaller**. Similar-size circles bounce off each other.
- ⚙ **Spinning saws** take 8% of a circle's score on each hit. At under 2 points the circle is knocked out.
- A knocked-out viewer comes back as soon as they tap, comment, or gift again.
- The **top 3 wear crowns**. The leaderboard (top-left) shows score and 💀 eats.

### 🎁 Gifts: cheap gifts count!

**1 coin = 50 points.** Even a single Rose matters. Every gift also triggers **every power at or below its level**, and a gift streak counts as one gift (5 Roses in a row = 5 coins = Shield).

| Gift size | New power unlocked | What it does |
|---|---|---|
| 1+ coin (Rose) | 🌹 Speed burst | Faster for 4s |
| 5+ coins | 💗 Shield | Can't be eaten or cut for 10s |
| 10+ coins | 🧲 Magnet | Pulls in energy dots **and smaller circles** for 10s |
| 30+ coins | 🌌 Shockwave | Blasts nearby circles away; smaller ones lose 15% |
| 99+ coins | ❄️ Freeze | **Everyone else** and the saws freeze for 5s |
| 199+ coins | 🎯 Hunter | Hunts smaller circles for 15s |
| 299+ coins | 🕳️ Black hole | Sucks every circle and dot toward you for 8s |
| 1,000+ coins | 👑 Arena King | **Doubles your score**, gold crown, 30s immune to everything |

**⚡ Power** also stacks with every gift, shown as a gold badge. Each point means a bit more speed, saw armor, and stealing points when bumping. At **⚡10** you get **🦈 Giant Jaws**: you can eat circles only 5% smaller.

**🏅 Supporter ranks:** total coins a viewer sends during the stream. A higher rank makes **every tap worth more**:

| Total coins | Rank | Taps worth |
|---|---|---|
| 10 | 🥉 Bronze | 1.5× |
| 50 | 🥈 Silver | 2× |
| 100 | 🥇 Gold | 3× |
| 300 | 💎 Diamond | 5× |
| 1,000 | 🔥 Legend | 10× |

The rank shows next to their name with a colored ring.

**💫 Revive:** if a viewer gets knocked out, any gift brings them back with **half their old points**.

**💰 Top gifter** of the stream is shown under the leaderboard.

---|---|---|---|
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

## 🔮 Zodiac teams (13 signs + Ophiuchus)

- Viewers **type their sign in chat** ("Scorpio", "leo", "♏", "team ophiuchus 🐍") to join that team. Their circle gets the sign's color and glyph.
- Or they **type their birthday** ("Dec 5", "December 5th", "12/5"). The game uses the StarChart13 13-sign dates and announces their **TRUE SKY** sign, e.g. *"not Sagittarius… TRUE SKY OPHIUCHUS ⛎"*.
- **✨ Zodiac Teams** on the leaderboard shows the top 3 signs (total points), and each round announces which sign wins.
- The background is a turning 13-sign zodiac wheel, and the leaderboard shows **"Free 13-sign chart: starchart13.com"**.

Birthday dates used: Capricorn Jan 19 · Aquarius Feb 16 · Pisces Mar 12 · Aries Apr 19 · Taurus May 14 · Gemini Jun 20 · Cancer Jul 21 · Leo Aug 10 · Virgo Sep 16 · Libra Oct 31 · Scorpio Nov 23 · **Ophiuchus Nov 30** · Sagittarius Dec 18.

## 🐍 The Ophiuchus serpent

A glowing serpent slithers around the arena the whole game. It often heads toward a circle to "bless" it. **Any circle that touches the serpent's HEAD gets +100 bonus points** (once every 4 seconds per circle). It never hurts anyone. The head has a pulsing gold ring so viewers can spot it. Change the bonus with `SNAKE_BONUS` in the code.

## 🎵 Music & 🗣️ announcer voice

- **Music:** "Action Dubstep" by The_Mountain (free-to-use track from Pixabay), stored in `music/action-dubstep.mp3`, looping. To change songs, upload a new MP3 to the `music` folder with the same name (or change `MUSIC_FILE` in the code). Use free-to-use music only; popular songs can get your LIVE muted.
- **Voice:** the computer's built-in text-to-speech announces things for you: *"Maria joined Team Scorpio!"*, *"Jen, you're not a Sagittarius. You're a true sky Ophiuchus!"*, *"big spender sent a Paper Crane! freeze all!"*, *"Thank you for the follow!"*, *"Team Pisces wins the round!"*. Music gets quieter while it talks. On Edge it uses a natural-sounding Microsoft voice when available.
- **Starting sound:** browsers need one click before they can play sound. In the LIVE version (`?live=1`), click the **🔊 CLICK TO START** box once, before you point your camera.
- **Keys:** **M** = music on/off · **V** = voice on/off. (Also in the 🎁 panel.)
- Turn the laptop volume up so your phone's mic picks it up.

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

## 🔴 Going LIVE for real (laptop + TikFinity)

The game can now read your **real** TikTok LIVE through **TikFinity**, a free streaming tool. TikFinity connects to your LIVE using only your @username, not your password, and passes viewers' taps, comments, follows and gifts (with their **profile pictures**) to the game.

**What you need:** a TikTok account that can go LIVE (1,000+ followers; 18+ to receive gifts), your laptop, **TikTok LIVE Studio** (TikTok's free PC streaming app), and the **TikFinity desktop app**.

**Setup (one time)**
1. Install **TikTok LIVE Studio** from TikTok's website and log in.
2. Install the **TikFinity** desktop app, log in, and enter your TikTok **@username**.
3. In LIVE Studio, set the layout to **portrait (vertical)** so it fills phones.
4. In LIVE Studio, add a source → **Link**, and paste the overlay link:
   **`https://lezkt1811-maker.github.io/circle-arena-live/?live=1`**
   This is the clean version: no buttons, no pretend viewers, and it connects to TikFinity automatically.

**Getting a sharp picture with your phone camera:** the LIVE version (`?live=1`) always draws the game in **phone shape (9:16)**, as tall as your screen. Press **F11** in Edge for full screen (F11 again to exit), point your phone's 1× back camera straight at it from about 8–12 inches, turn **Enhance/beauty filters off** in TikTok, put laptop brightness at max, and tap the game on your phone to focus.

**Every time you stream**
1. Open TikFinity.
2. Go LIVE in LIVE Studio.
3. In TikFinity, press **Connect** for your LIVE.
4. The game connects within a few seconds. Viewers join by tapping, commenting or gifting.
5. **Host it!** Talk, call out the leader, thank gifters, and hype the rounds.

**Testing first (not live):** open the normal game link, tap 🎁, scroll to **REAL LIVE CONNECTION**, and press **CONNECT TO TIKFINITY**. It says ✅ Connected when TikFinity is running. If TikFinity shows a different local address in its settings, paste that into **Address**. The default is `ws://localhost:21213/`. If Chrome asks to allow access to devices on your local network, allow it.

**Real gifts:** any TikTok gift works. Its coin value decides the points and powers, using the table above.

Gift streaks (like 10 Roses in a row) count once, when the streak ends.

**Small laptop tips:** close other programs while streaming, and keep LIVE Studio at 720p if it's slow.

> ⚠️ **TikTok's rules:** TikTok's in-app LIVE rules include a section on "Inauthentic gift requests." Read it before streaming: Profile → menu → Creator Tools → LIVE Center → Rules and Guidance. Host the game actively instead of leaving it running unattended, and don't promise prizes for gifts.

## 🔌 How the connection works (for developers)

The game listens for events in one place (`LiveEvents`). The TikFinity bridge (`Bridge` in the code) turns TikFinity / TikTok-Live-Connector style messages into these events. It also accepts this simpler format directly, so any relay can be used:

```js
{ "type": "like",    "user": "name", "count": 15 }
{ "type": "join",    "user": "name" }
{ "type": "follow",  "user": "name" }
{ "type": "comment", "user": "name", "comment": "hi!" }
{ "type": "gift",    "user": "name", "coins": 100, "giftName": "Galaxy" }
```

TikTok doesn't offer an official public API for LIVE events. Tools like TikFinity read the public LIVE data. Use them in line with TikTok's terms.

## 🌐 Future: Cloudflare Workers

A Cloudflare Worker (with a Durable Object) could be that relay. It would receive LIVE events, run one shared arena, and send the same game to every screen watching. That way a viewer could open the link and watch their own circle live. The game logic is kept separate from the drawing code so it can move to a server later. None of this is needed for the current version.

---

Original design and code. HTML5 Canvas + vanilla JavaScript.
