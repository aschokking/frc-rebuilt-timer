# FRC 2026 Match Timer

A static website that displays a countdown timer for the 2026 FRC game with visual indicators for each match phase.

## Project Overview

Build a single-page static website that:
- Displays a large, readable countdown timer
- Shows the current match phase prominently
- Provides visual/audio cues when phases change
- Works well on various screen sizes (designed for projector/TV display)

## Match Structure

The 2026 FRC match is 2:40 total (160 seconds):

### AUTO Period (20 seconds)
| Phase | Duration | Timer Display |
|-------|----------|---------------|
| AUTO  | 20s      | 0:20 → 0:00   |

### TELEOP Period (2:20 = 140 seconds)
| Phase            | Duration | Timer Display |
|------------------|----------|---------------|
| TRANSITION SHIFT | 10s      | 2:20 → 2:10   |
| SHIFT 1          | 25s      | 2:10 → 1:45   |
| SHIFT 2          | 25s      | 1:45 → 1:20   |
| SHIFT 3          | 25s      | 1:20 → 0:55   |
| SHIFT 4          | 25s      | 0:55 → 0:30   |
| END GAME         | 30s      | 0:30 → 0:00   |

## Technical Requirements

### Stack
- Single HTML file with embedded CSS and JavaScript
- No build tools or frameworks required
- No external dependencies (fully offline-capable)
- Easy to deploy to a free static hosting service

### Features
1. **Start/Stop/Reset controls** - Simple button controls
2. **Large timer display** - Should be readable from across a room
3. **Phase indicator** - Current phase name displayed prominently
4. **Phase progress** - Visual indicator of progress through current phase
5. **Color coding** - Different colors for different phases:
   - AUTO: Yellow/Gold
   - TRANSITION SHIFT: Orange
   - SHIFTS 1-4: Blue (or cycling colors)
   - END GAME: Red
6. **Audio cues** (optional) - Beeps or tones at phase transitions
7. **Keyboard shortcuts** - Space to start/stop, R to reset

### Display Layout
Show the phases and where the timer is currently at in a horizontal bar or list format, with the current phase highlighted.

## File Structure

```
/
├── index.html    # Single file containing everything
└── CLAUDE.md     # This file
```

## Development Notes

- Timer should use requestAnimationFrame or setInterval with drift correction
- Consider using the Web Audio API for reliable audio cues
- Test at various window sizes for projector use
- The timer counts DOWN (not up)
- AUTO counts down separately, then TELEOP starts fresh at 2:20