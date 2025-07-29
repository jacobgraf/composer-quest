# Composer Quest: The Battle of the Packages

A browser-based game for Laracon 2025 Game Jam where you play as a Laravel "Composer" managing package dependencies!

## 🎮 Game Overview

**Objective**: Sort Laravel packages for 60 seconds! Accept valid packages (✅) and reject fake/malicious ones (❌) to achieve package harmony.

**Theme**: You are the Composer conducting an orchestra of packages. Keep the harmony going by making the right choices!

## 🎯 How to Play

1. **Start the Game**: Click "Start Game" on the welcome screen
2. **Sort Packages**: Packages fall from the top with names like:
   - ✅ Valid: `spatie/laravel-permission`, `livewire/livewire`, `laravel/sanctum`
   - ❌ Fake: `laravel/virus`, `hacker/exploit`, `malware/backdoor`
3. **Controls**:
   - Click ✅ (Accept) or ❌ (Reject) buttons
   - Keyboard: Left Arrow/A = Accept, Right Arrow/D = Reject
   - Mobile: Touch the buttons
4. **Special Events**: Watch for "DEPENDENCY CONFLICTS" - click RESOLVE quickly for bonus points!
5. **Easter Eggs**: Build streaks to see Laravel-themed messages like "Taylor Otwell approves!"

## 🏆 Scoring System

- **Correct Choice**: +10 points (+ streak bonus)
- **Wrong Choice**: -5 points (resets streak)
- **Streak Bonus**: +5 points per streak level
- **Dependency Conflict**: +20 points for quick resolution
- **Missing Package**: Resets streak

## 🎨 Features

- **Retro Pixel Art Style**: Classic 8-bit aesthetic with pixel fonts
- **Responsive Design**: Works on desktop and mobile
- **Audio Feedback**: Sound effects for correct/wrong choices
- **High Score System**: Local leaderboard stored in browser
- **Laravel Easter Eggs**: Fun messages and references
- **Progressive Difficulty**: Packages fall faster as score increases

## 🚀 Deployment

### Recommended Static Hosting Options

**GitHub Pages** (Free):

1. Push to GitHub repository
2. Enable GitHub Pages in repository settings
3. Access via `https://username.github.io/composer-quest`

**Netlify** (Free):

1. Drag and drop the project folder to Netlify
2. Instant deployment with custom domain support
3. Automatic HTTPS and global CDN

**Vercel** (Free):

1. Connect GitHub repository or upload files
2. Zero-config deployment for static sites
3. Automatic deployments on git push

**Surge.sh** (Free):

```bash
npm install -g surge
cd composer-quest
surge
```

**Any Web Server**:

- Upload files to any web hosting service
- No server-side requirements - pure static files

### Local Testing

```bash
# Simply open the file in any modern browser
open index.html

# Or serve with a local server
python -m http.server 8000
# Then visit http://localhost:8000
```

### File Structure

```
composer-quest/
├── index.html              # Main game file
├── assets/
│   ├── conductor.png        # Player character image
│   ├── package-delivery.png # Package icon
│   ├── applause.mp3         # Success sound
│   └── dissonant.mp3        # Error sound
├── memory-bank/             # Project documentation
└── README.md               # This file
```

## 🛠️ Technical Details

- **Frontend**: Vanilla JavaScript, HTML5, CSS3
- **Styling**: Tailwind CSS (via CDN)
- **Audio**: HTML5 Audio API
- **Storage**: localStorage for high scores
- **Compatibility**: Modern browsers (Chrome, Firefox, Safari, Edge)
- **Mobile**: Touch-friendly responsive design

## 🎵 Package Dataset

The game includes 32 carefully curated package names:

**Valid Laravel Packages** (16):

- spatie/laravel-permission
- livewire/livewire
- laravel/sanctum
- laravel/telescope
- barryvdh/laravel-debugbar
- intervention/image
- spatie/laravel-backup
- laravel/horizon
- And more...

**Fake/Malicious Packages** (16):

- laravel/virus
- hacker/exploit
- malware/backdoor
- fake/laravel-auth
- And more suspicious names...

## 🏅 Achievement Messages

- **Streak 5**: "Taylor Otwell approves!"
- **Streak 10**: "Artisan command executed!"
- **Streak 15**: "Package harmony achieved!"
- **High Scores**: "Excellent Composer!", "Great Package Management!"

## 🎮 Game Jam Requirements

✅ **Hosted online** - Ready for static hosting (GitHub Pages, Netlify, Vercel)
✅ **Playable in <5 minutes** - 60-second rounds
✅ **Vanilla JS + Tailwind** - No frameworks
✅ **Hostable on Laravel Cloud** - Single HTML file (though static hosting is more appropriate)
✅ **Creative image use** - Conductor & package delivery themes
✅ **Cross-browser compatible** - Modern web standards
✅ **Fun & memorable** - Laravel developer humor
✅ **Laravel themed** - Package management concept

## 🎯 Tips for High Scores

1. **Learn the Packages**: Memorize common Laravel packages
2. **Build Streaks**: Consecutive correct answers give bonus points
3. **Quick Reflexes**: Resolve dependency conflicts fast
4. **Stay Focused**: Don't let packages fall off screen
5. **Practice**: The game gets faster as you score higher!

## 🐛 Browser Support

- **Chrome/Chromium**: Full support
- **Firefox**: Full support
- **Safari**: Full support
- **Edge**: Full support
- **Mobile browsers**: Touch controls enabled

## 📱 Mobile Experience

- Large touch targets for easy tapping
- Responsive layout optimized for portrait mode
- Touch-friendly button spacing
- Swipe gestures (future enhancement)

---

**Made with ❤️ for the Laravel community and Laracon 2025 Game Jam**

_May your dependencies always resolve and your packages never conflict!_ 🎼📦
