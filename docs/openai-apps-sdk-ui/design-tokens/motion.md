# Motion

> Animation timing functions and durations

## Timing Functions

### Cubic Bezier Curves

| Token | Value | Description |
|-------|-------|-------------|
| `--cubic-enter` | `cubic-bezier(0.19, 1, 0.22, 1)` | Smooth entrance animations |
| `--cubic-exit` | `cubic-bezier(0.8, 0, 0.4, 1)` | Smooth exit animations |
| `--cubic-exit-snappy` | `cubic-bezier(0.65, 0, 0.4, 1)` | Snappier exit (less inertia delay) |
| `--cubic-move` | `cubic-bezier(0.65, 0, 0.35, 1)` | Movement/repositioning |

### Basic Timing

| Token | Value |
|-------|-------|
| `--transition-ease-basic` | `ease` |
| `--transition-duration-basic` | `150ms` |

## Usage Examples

### Enter Animation

```css
.element-enter {
  opacity: 0;
  transform: scale(0.95);
}

.element-enter-active {
  opacity: 1;
  transform: scale(1);
  transition: opacity 300ms var(--cubic-enter),
              transform 300ms var(--cubic-enter);
}
```

### Exit Animation

```css
.element-exit {
  opacity: 1;
  transform: scale(1);
}

.element-exit-active {
  opacity: 0;
  transform: scale(0.95);
  transition: opacity 200ms var(--cubic-exit),
              transform 200ms var(--cubic-exit);
}
```

### Basic Hover Transition

```css
.button {
  transition: background-color var(--transition-duration-basic) var(--transition-ease-basic);
}

.button:hover {
  background-color: var(--color-background-primary-soft-hover);
}
```

### Movement Animation

```css
.sliding-panel {
  transition: transform 400ms var(--cubic-move);
}

.sliding-panel.open {
  transform: translateX(0);
}

.sliding-panel.closed {
  transform: translateX(-100%);
}
```

## Recommended Durations

| Use Case | Duration |
|----------|----------|
| Micro-interactions (hover, focus) | `100-150ms` |
| Small transitions (buttons, inputs) | `150-200ms` |
| Medium transitions (dropdowns, tooltips) | `200-300ms` |
| Large transitions (modals, panels) | `300-400ms` |
| Page transitions | `400-600ms` |

## Animation Guidelines

1. **Use `--cubic-enter` for entrances** - Creates a smooth, decelerating motion
2. **Use `--cubic-exit` for exits** - Creates an accelerating motion that feels natural
3. **Use `--cubic-move` for repositioning** - Balanced easing for movement
4. **Keep micro-interactions fast** - Use `--transition-duration-basic` (150ms)
5. **Stagger complex animations** - Use `delay` for sequential animations
