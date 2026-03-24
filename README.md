[SPEC.md](https://github.com/user-attachments/files/26222931/SPEC.md)
# TypeRacer Arena - Typing Game Specification

## Concept & Vision

A high-energy, arcade-style typing game that feels like a retro racing game meets synthwave aesthetics. Players race against time to type words correctly, building combos and chasing high scores. The experience should feel fast, rewarding, and addictive - with visual feedback that makes every correct keystroke satisfying and every mistake feel like a learning moment.

## Design Language

**Aesthetic Direction:** Retro arcade meets synthwave - neon colors on dark backgrounds, CRT-style effects, glowing text, and pulsing animations. Think: arcade cabinet in a 1980s vision of the future.

**Color Palette:**
- Primary: `#ff006e` (hot pink)
- Secondary: `#00f5d4` (cyan)
- Accent: `#fee440` (electric yellow)
- Background: `#0d0221` (deep purple-black)
- Surface: `#150734` (elevated purple)
- Success: `#00ff88` (neon green)
- Error: `#ff3366` (neon red)
- Text: `#ffffff` (white)

**Typography:**
- Display: 'Orbitron' (futuristic, tech feel)
- Body: 'Share Tech Mono' (monospace for typing)
- Fallback: monospace

**Motion Philosophy:**
- Pulse animations on active elements
- Shake effect on errors
- Satisfying scale-up on correct keystrokes
- Countdown with dramatic scaling
- Combo counter with bounce effects
- Screen flash on mistakes
- Particle effects on word completion

## Layout & Structure

1. **Start Screen** - Animated title, typing speed selector, start button with glow effect
2. **Game Screen** - Current word display, input area, stats (WPM, accuracy, combo, score, time)
3. **Results Screen** - Final score breakdown, stats summary, play again option

**Visual Pacing:**
- Start screen: calm, inviting glow
- Game screen: intense, focused, minimal distractions
- Results: celebratory or encouraging based on performance

## Features & Interactions

### Core Gameplay
- Words appear one at a time for typing
- Timer counts down from 60 seconds
- WPM calculated in real-time
- Accuracy percentage tracked
- Combo system: consecutive correct words increase multiplier (1x → 2x → 3x → 4x)
- Combo breaks on mistakes (wrong letter or timeout)
- Words get longer/harder as score increases

### Word System
- Curated word lists: easy (3-4 letters), medium (5-6 letters), hard (7+ letters)
- Mix of common words and fun challenges
- No repeated words until pool exhausted

### Difficulty Progression
- Easy: First 5 words or first 500 points
- Medium: 500-1500 points
- Hard: 1500+ points

### Input Behavior
- Auto-focus on input field
- Enter not required - auto-advances on correct word
- Visual feedback for each keystroke (correct = green, wrong = red)
- Current character highlighted
- Cannot type beyond word length

### Scoring
- Base points = word length × 10
- Combo multiplier applied
- Bonus points for accuracy (100% = 50 bonus per word)
- Speed bonus: completing word under 1 second = 20 bonus

### Stats Display
- Current WPM (rolling average)
- Accuracy percentage
- Current combo
- Score
- Time remaining
- Words completed

## Component Inventory

### Start Screen
- Animated title with glow effect
- Subtitle: "Test your typing speed!"
- "START" button with pulsing border
- Brief instructions

### Game HUD
- **Word Display:** Large, centered word with character-by-character highlighting
- **Input Field:** Styled text input, invisible border, glowing focus state
- **Stats Bar:** Flexbox row with icon + value pairs
- **Combo Display:** Large multiplier badge that scales on increase
- **Timer:** Circular progress indicator or countdown with color change

### Results Screen
- "GAME OVER" title
- Final score (large, animated count-up)
- Stats grid: WPM, Accuracy, Words, Best Combo
- Performance message (based on WPM tier)
- "PLAY AGAIN" button

### Visual Effects
- Screen shake on error
- Neon glow pulses
- Particle burst on combo milestones (5, 10, 15...)
- CRT scanline overlay (subtle)
- Background grid animation

## Technical Approach

- Single HTML file with embedded CSS and JS
- Vanilla JavaScript (no frameworks)
- CSS animations and transitions
- RequestAnimationFrame for smooth timer
- LocalStorage for high score persistence
- Web Audio API for sound effects (optional enhancement)
- Responsive: works on mobile with virtual keyboard
