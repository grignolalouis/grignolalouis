# Shadows & Elevation

> Shadow tokens and elevation levels

## Shadow System

Shadows are built from geometry tokens and alpha values that adapt to light/dark themes.

### Shadow Geometry

| Token | Value |
|-------|-------|
| `--elevation-100-geo` | `0 1px 2px -1px` |
| `--elevation-200-geo` | `0 2px 4px -1px` |
| `--elevation-300-geo` | `0 4px 8px -2px` |
| `--elevation-400-geo` | `0 8px 16px -4px` |

### Shadow Alpha (Light Theme)

| Token | Value |
|-------|-------|
| `--shadow-alpha-100` | `0.08` |
| `--shadow-alpha-200` | `0.08` |
| `--shadow-alpha-300` | `0.10` |
| `--shadow-alpha-400` | `0.12` |

### Shadow Alpha (Dark Theme)

| Token | Value |
|-------|-------|
| `--shadow-alpha-100` | `0.20` |
| `--shadow-alpha-200` | `0.20` |
| `--shadow-alpha-300` | `0.36` |
| `--shadow-alpha-400` | `0.30` |

## Elevation Tokens

### Level 100 (Subtle)

| Token | Description |
|-------|-------------|
| `--shadow-100` | Base shadow |
| `--shadow-100-strong` | 1.25x intensity |
| `--shadow-100-stronger` | 1.6x intensity |

### Level 200 (Default)

| Token | Description |
|-------|-------------|
| `--shadow-200` | Base shadow |
| `--shadow-200-strong` | 1.25x intensity |
| `--shadow-200-stronger` | 1.6x intensity |

### Level 300 (Elevated)

| Token | Description |
|-------|-------------|
| `--shadow-300` | Base shadow |
| `--shadow-300-strong` | 1.25x intensity |
| `--shadow-300-stronger` | 1.6x intensity |

### Level 400 (High)

| Token | Description |
|-------|-------------|
| `--shadow-400` | Base shadow |
| `--shadow-400-strong` | 1.25x intensity |
| `--shadow-400-stronger` | 1.6x intensity |

## Hairline Shadow

For subtle edge definition:

| Token | Light Theme | Dark Theme |
|-------|-------------|------------|
| `--shadow-hairline-width` | `1px` (0.5px @1.5x) | `1px` (0.5px @1.5x) |
| `--shadow-hairline-color` | `rgb(0 0 0 / 8%)` | `rgb(255 255 255 / 10%)` |
| `--shadow-hairline` | `0 0 0 var(--shadow-hairline-width) var(--shadow-hairline-color)` |

## General Shadow

| Token | Light Theme | Dark Theme |
|-------|-------------|------------|
| `--shadow` | `0 10px 15px -3px rgba(0 0 0 / 10%), 0 4px 6px -4px rgba(0 0 0 / 10%)` | `0 10px 15px -3px rgba(0 0 0 / 20%), 0 4px 6px -4px rgba(0 0 0 / 20%)` |

## Usage Examples

```css
/* Subtle elevation */
.card {
  box-shadow: var(--shadow-100);
}

/* Default elevation */
.dropdown {
  box-shadow: var(--shadow-200);
}

/* High elevation (modals, popovers) */
.modal {
  box-shadow: var(--shadow-400);
}

/* With hairline for edge definition */
.panel {
  box-shadow: var(--shadow-hairline), var(--shadow-200);
}

/* Stronger shadow for emphasis */
.floating-action {
  box-shadow: var(--shadow-300-strong);
}
```
