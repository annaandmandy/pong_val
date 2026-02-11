# 💝 Valentine's Pong Gacha Game

**🎮 Play Now: [https://annaandmandy.github.io/pong_val/](https://annaandmandy.github.io/pong_val/)**

---

## 🎮 Game Overview

This is a unique four-layer Valentine's Day gift experience combining **Pong Game** + **Gacha System** + **Card Collection**. Your boyfriend needs to play Pong to earn tokens, then use those tokens to draw Pokemon-style cards featuring your memories together, and ultimately unlock the grand prize - a real-world treasure clue!

---

## 🎯 Four-Layer Experience Design

### Layer 1: 🎁 Mystery Landing Page
- Opens with a mysterious challenge message
- Click "Unlock" button to enter the game
- Creates anticipation and ritual sense

### Layer 2: 🎮 Token Earning (Game)
- Classic Pong game with romantic theme
- Win 1 ball = +1 Token 💰
- High-speed return (1.5x+ speed) = +2 Tokens (Bonus!)
- Tokens permanently saved (localStorage)
- Pause/Resume/Restart anytime

### Layer 3: 🎰 Gacha Card Drawing
- 5 Tokens = 1 draw
- 4 rarity levels: R / SR / SSR / UR
- Pity system: Guaranteed UR within 5 draws
- Animation effects: shake, flip, glow
- Drawn cards automatically saved

### Layer 4: 🏆 Grand Prize
- Special full-screen animation when drawing UR card
- Shows your most romantic message
- Reveals real-world treasure clue
- Can continue playing to collect other cards

---

## 📊 Gacha Probability System

| Rarity | Probability | Card Count | Theme |
|--------|------------|------------|-------|
| **R** (Common) | 40% | 4 cards | Daily memories |
| **SR** (Rare) | 40% | 3 cards | Special romantic moments |
| **SSR** (Epic) | 15% | 2 cards | Epic memories |
| **UR** (Legendary) | 5% | 1 card | **Ultimate Prize (Your confession)** |

**Pity System:** If you don't get UR in 5 draws, the 5th draw is guaranteed UR!

---

## 💰 Token System

### How to Earn Tokens
1. **Win Points:** Each point won against AI = +1 Token
2. **High-Speed Return:** Successfully return ball at ≥1.5x speed = +1 extra Token (total +2)
3. **Endurance:** Ball speed increases by 10% every 10 seconds for extra challenge

### Token Spending
- Each gacha draw costs 5 Tokens
- Tokens are permanently saved, even after closing the page

---

## 🎴 Card Collection

All cards feature your real memories with Pokemon-style attacks:

### R Cards (Common)
- **Zootopia Duo** - Wearing Judy & Nick hats
- **Failed Lifter** - His failed attempt to carry you
- **BL Gamers** - Gaming together
- **Ice Crashers** - Ice skating tumble

### SR Cards (Rare)
- **Chucky Twins** - Halloween Chucky costumes
- **Lobster Devourers** - Lobster feast
- **Pocky Challengers** - Playing Pocky game

### SSR Cards (Epic)
- **Cheek Smoocher** - Kiss on the cheek
- **Snow Angel Master** - Making snow angels

### UR Card (Legendary)
- **Kitty Light Duo** - The hugging kitty lights

Each card has two attack moves like Pokemon cards!

---

## 🚀 How to Run

### Local Testing
```bash
cd /Volumes/T7/pong_val
python3 -m http.server 8080
```

Then open in browser: `http://localhost:8080`

### Deploy to GitHub Pages
1. Create a GitHub repository
2. Upload all files (including `assets` folder)
3. Enable GitHub Pages in repository settings
   - Go to Settings → Pages
   - Source: Branch `main`, Folder `/ (root)`
   - Click Save
4. Your site will be live at: `https://YOUR_USERNAME.github.io/REPO_NAME/`

**Current Deployment:** [https://annaandmandy.github.io/pong_val/](https://annaandmandy.github.io/pong_val/)

---

## 🎮 Game Controls

### Desktop Controls
- **Single Player:** W/S keys to control your paddle
- **Two Player:**
  - Player 1: W/S keys
  - Player 2: Up/Down arrow keys

### Mobile Controls
- Touch and drag the paddle

### Game Buttons
- **Pause/Resume:** Pause game without affecting timer
- **Restart:** Reset score and speed, but keep tokens
- **Draw:** Open gacha interface (requires 5 tokens)
- **Collection:** View all unlocked cards

---

## 🔧 Technical Implementation

### Core Features
- ✅ 4-layer game state system (LANDING → GAME → GACHA → PRIZE)
- ✅ Token system with localStorage persistence
- ✅ Gacha probability system (40/40/15/5 with 5-draw pity)
- ✅ Card collection system (10 cards, shows collection progress)
- ✅ Animation effects (shake, flip, glow, heartbeat)
- ✅ Sound effects (hit, score, grand prize)
- ✅ Responsive design (supports mobile and desktop)
- ✅ Pokemon-style card design with attack moves

### Data Persistence
All progress saved in browser's localStorage:
- `loveTokens` - Token count
- `unlockedCards` - List of unlocked cards
- `pityCounter` - Pity counter
- `urUnlocked` - Whether UR card is unlocked

---

## 🎨 Customization

### Modify Confession Message
In [index.html](index.html), find the `showGrandPrize()` function:

```javascript
prizeMessage.innerHTML = `
    <span class="heart">💝</span><br>
    You've won all my love!<br>  ← Modify here
    <span class="heart">💝</span>
`;

prizeClue.innerHTML = `
    <strong>🎁 Real World Treasure Clue:</strong><br>
    "The gift is hidden in..."<br>  ← Modify here
    <br>
    <small>Happy Valentine's Day, my love ❤️</small>
`;
```

### Modify Card Content
Edit [cards-config.json](cards-config.json) to change card names, titles, attacks, and images.

---

## 📱 Testing Checklist

### Basic Tests
- [ ] Open website, see landing page
- [ ] Click "Unlock" button, enter game
- [ ] See token display (top right)
- [ ] See collection button (top left)

### Game Tests
- [ ] Control paddle with W/S keys
- [ ] Token +1 after winning point
- [ ] Token +2 after high-speed return
- [ ] Pause/Resume works

### Gacha Tests
- [ ] After 5 tokens, "Draw" button is clickable
- [ ] Click to enter gacha screen
- [ ] Click "Draw Once" to see shake animation
- [ ] Display drawn card with rarity colors
- [ ] Tokens correctly deducted (-5)

### Collection Tests
- [ ] Click "Collection" button to open album
- [ ] See all 10 cards (unlocked in color, locked in gray)
- [ ] Display collection progress (e.g., 3/10, 30%)

### UR Prize Tests
- [ ] After drawing UR, auto-jump to prize screen
- [ ] Display confession message and treasure clue
- [ ] Click "Continue Collecting" to return to game

### Persistence Tests
- [ ] Close webpage, reopen
- [ ] Token count preserved
- [ ] Unlocked cards preserved

---

## 🐛 Troubleshooting

### Q: Nothing shows when opening webpage
A: Check browser console (F12) for error messages

### Q: Images not displaying
A:
1. Confirm image files are in correct location (`assets/cards/`)
2. Confirm filenames match exactly (case sensitive!)
3. Clear browser cache and reload
4. Without images, game will show colored placeholders (normal behavior)

### Q: Tokens not saving
A: Confirm browser allows localStorage (private mode may disable it)

### Q: Can't draw UR card
A:
- Probability is 5%, average needs 20 draws
- Pity system: Maximum 5 draws guarantees UR
- Check pity progress in console: `game.pityCounter`

---

## 💝 Message to Your Boyfriend

Dear,

This is a special Valentine's Day gift I prepared for you. I spent a lot of time designing this game, hoping you can feel my heart.

Every card represents my love for you. I hope while collecting these cards, you'll remember the beautiful moments we've shared together.

When you draw that golden UR card, that's what I want to say to you.

Happy Valentine's Day, my love! ❤️

---

## 📚 File Index

- [index.html](index.html) - Main game file
- [cards-config.json](cards-config.json) - Card data configuration
- [README.md](README.md) - This file (project documentation)
- [CARD_CUSTOMIZATION_GUIDE.md](CARD_CUSTOMIZATION_GUIDE.md) - Card customization guide

---

## 🎯 Future Enhancement Ideas (Optional)

If you want to further improve:

1. **Music:** Add background music (Audio API)
2. **Effects:** Add particle effects when drawing UR
3. **Animation:** Envelope opening animation (CSS or SVG)
4. **Multilingual:** Chinese/English toggle
5. **Share Function:** Let him share collection progress
6. **Achievement System:** Special reward for completing full collection

---

**Created with ❤️ for a very special Valentine's Day**

**🎮 Play Now: [https://annaandmandy.github.io/pong_val/](https://annaandmandy.github.io/pong_val/)**
