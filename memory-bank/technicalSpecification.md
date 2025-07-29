# Technical Specification - Composer Quest

2025-07-29 12:09:50 - Detailed technical specification for implementation phase.

## File Structure

```
/
├── index.html (main game file)
├── assets/
│   ├── conductor.png (player character)
│   ├── package-delivery.png (falling packages)
│   ├── applause.mp3 (correct answer sound)
│   ├── dissonant.mp3 (wrong answer sound)
│   └── background.mp3 (classical background music)
├── memory-bank/ (project documentation)
└── README.md
```

## Game Data Structure

### Package Dataset

```javascript
const packages = [
  // Valid Laravel Packages
  { name: "spatie/laravel-permission", valid: true },
  { name: "livewire/livewire", valid: true },
  { name: "laravel/sanctum", valid: true },
  { name: "laravel/telescope", valid: true },
  { name: "barryvdh/laravel-debugbar", valid: true },
  { name: "intervention/image", valid: true },
  { name: "spatie/laravel-backup", valid: true },
  { name: "laravel/horizon", valid: true },
  { name: "spatie/laravel-activitylog", valid: true },
  { name: "laravel/cashier", valid: true },

  // Fake/Malicious Packages
  { name: "laravel/virus", valid: false },
  { name: "hacker/exploit", valid: false },
  { name: "malware/backdoor", valid: false },
  { name: "fake/laravel-auth", valid: false },
  { name: "suspicious/package", valid: false },
  { name: "evil/composer", valid: false },
  { name: "trojan/laravel", valid: false },
  { name: "phishing/framework", valid: false },
];
```

### Game State Object

```javascript
const gameState = {
  score: 0,
  timeLeft: 60,
  streak: 0,
  packages: [],
  isPlaying: false,
  isPaused: false,
  gameSpeed: 1,
  packageSpawnRate: 2000, // milliseconds
  lastSpawn: 0,
};
```

## HTML Structure

### Main Layout

- Header: Score, Timer, Streak display
- Game Area: Falling packages container
- Player Area: Conductor character with Accept/Reject buttons
- UI Overlays: Start screen, Game Over screen, Easter egg popups

### Key Elements

- `#gameContainer` - Main game viewport
- `#conductor` - Player character image
- `#acceptBtn` - Green checkmark button
- `#rejectBtn` - Red X button
- `#score` - Score display
- `#timer` - Countdown timer
- `#streak` - Current streak counter

## CSS Classes (Tailwind)

### Layout Classes

- `container mx-auto` - Centered game container
- `flex flex-col items-center` - Vertical layout
- `bg-gradient-to-b from-yellow-400 to-orange-500` - Background gradient
- `fixed inset-0` - Full screen overlays

### Animation Classes

- `animate-bounce` - Package falling animation
- `animate-pulse` - Button feedback
- `transition-all duration-300` - Smooth transitions
- `transform scale-110` - Hover effects

### Responsive Classes

- `sm:text-lg md:text-xl lg:text-2xl` - Responsive text
- `px-4 sm:px-6 md:px-8` - Responsive padding

## JavaScript Architecture

### Core Functions

1. `initGame()` - Initialize game state and event listeners
2. `startGame()` - Begin gameplay loop
3. `spawnPackage()` - Create new falling package
4. `updatePackages()` - Move packages and check collisions
5. `handlePackageClick(packageId, action)` - Process user input
6. `updateScore(points)` - Modify score and streak
7. `checkGameEnd()` - Monitor timer and end conditions
8. `showGameOver()` - Display final score screen

### Event Handlers

- Click events for Accept/Reject buttons
- Touch events for mobile support
- Keyboard events for accessibility
- Window resize for responsive layout

### Animation Loop

```javascript
function gameLoop(timestamp) {
  if (gameState.isPlaying) {
    updatePackages(timestamp);
    updateTimer();
    checkSpecialEvents();
    render();
  }
  requestAnimationFrame(gameLoop);
}
```

## Audio System

### Sound Effects

- `applause.mp3` - Correct package selection
- `dissonant.mp3` - Wrong package selection
- `background.mp3` - Looping classical music

### Audio Implementation

```javascript
const audio = {
  applause: new Audio("assets/applause.mp3"),
  dissonant: new Audio("assets/dissonant.mp3"),
  background: new Audio("assets/background.mp3"),
};
```

## Scoring System

### Point Values

- Correct package: +10 points
- Wrong package: -5 points
- Streak bonus: +5 points per streak level
- Dependency conflict resolved: +20 points

### Streak Mechanics

- Increment on correct answers
- Reset to 0 on wrong answers
- Easter egg at streak 5, 10, 15+

## Special Events

### Dependency Conflicts

- Random event every 15-20 seconds
- Large "RESOLVE" button appears
- 3-second time limit to click
- Bonus points for quick resolution

### Easter Eggs

- "Taylor Otwell approves!" at streak milestones
- "Artisan command executed!" on special scores
- "Package harmony achieved!" on perfect streaks

## Mobile Optimization

### Touch Controls

- Large touch targets (minimum 44px)
- Swipe gestures for package sorting
- Haptic feedback on supported devices

### Responsive Design

- Scalable UI elements
- Optimized for portrait orientation
- Touch-friendly button spacing

## Performance Considerations

### Optimization Strategies

- Object pooling for packages
- Efficient DOM manipulation
- RequestAnimationFrame for smooth animation
- Preloaded audio assets
- Minimal CSS animations

### Browser Compatibility

- Modern browsers (ES6+ support)
- Fallbacks for older browsers
- Progressive enhancement approach
