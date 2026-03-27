# Typography

> Font families, sizes, weights, and line heights

## Font Families

| Token | Value |
|-------|-------|
| `--font-sans` | `ui-sans-serif, -apple-system, system-ui, "Segoe UI", "Noto Sans", "Helvetica", "Arial", "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", sans-serif` |
| `--font-mono` | `ui-monospace, "SFMono-Regular", "SF Mono", "Menlo", "Monaco", "Consolas", "Liberation Mono", "DejaVu Sans Mono", "Courier New", monospace` |
| `--font-serif` | `initial` |

## Font Weights

| Token | Value |
|-------|-------|
| `--font-weight-normal` | `400` |
| `--font-weight-medium` | `500` |
| `--font-weight-semibold` | `600` |
| `--font-weight-bold` | `700` |

## Letter Spacing (Tracking)

| Token | Value |
|-------|-------|
| `--font-tracking-wide` | `0em` |
| `--font-tracking-normal` | `0em` |
| `--font-tracking-tight` | `0em` |

## Heading Styles

| Token | Size | Line Height | Weight |
|-------|------|-------------|--------|
| `--font-heading-5xl-*` | `4.5rem` (72px) | `4.5rem` (72px) | semibold |
| `--font-heading-4xl-*` | `3.75rem` (60px) | `3.75rem` (60px) | semibold |
| `--font-heading-3xl-*` | `3rem` (48px) | `3rem` (48px) | semibold |
| `--font-heading-2xl-*` | `2.25rem` (36px) | `2.625rem` (42px) | semibold |
| `--font-heading-xl-*` | `2rem` (32px) | `2.375rem` (38px) | semibold |
| `--font-heading-lg-*` | `1.5rem` (24px) | `1.75rem` (28px) | semibold |
| `--font-heading-md-*` | `1.25rem` (20px) | `1.625rem` (26px) | semibold |
| `--font-heading-sm-*` | `1.125rem` (18px) | `1.625rem` (26px) | semibold |
| `--font-heading-xs-*` | `1rem` (16px) | `1.5rem` (24px) | semibold |

### Heading Token Structure

Each heading size has these tokens:

```css
--font-heading-{size}-size
--font-heading-{size}-line-height
--font-heading-{size}-weight
--font-heading-{size}-tracking
```

### Usage Example

```css
.heading-lg {
  font-size: var(--font-heading-lg-size);
  line-height: var(--font-heading-lg-line-height);
  font-weight: var(--font-heading-lg-weight);
  letter-spacing: var(--font-heading-lg-tracking);
}
```

## Text Styles

| Token | Size | Line Height | Weight |
|-------|------|-------------|--------|
| `--font-text-lg-*` | `1.125rem` (18px) | `1.8125rem` (29px) | normal |
| `--font-text-md-*` | `1rem` (16px) | `1.5rem` (24px) | normal |
| `--font-text-sm-*` | `0.875rem` (14px) | `1.25rem` (20px) | normal |
| `--font-text-xs-*` | `0.75rem` (12px) | `1.125rem` (18px) | normal |
| `--font-text-2xs-*` | `0.625rem` (10px) | `0.875rem` (14px) | normal |
| `--font-text-3xs-*` | `0.5rem` (8px) | `0.75rem` (12px) | normal |

### Text Token Structure

Each text size has these tokens:

```css
--font-text-{size}-size
--font-text-{size}-line-height
--font-text-{size}-weight
--font-text-{size}-tracking
```

### Usage Example

```css
.body-text {
  font-size: var(--font-text-md-size);
  line-height: var(--font-text-md-line-height);
  font-weight: var(--font-text-md-weight);
}

.caption {
  font-size: var(--font-text-xs-size);
  line-height: var(--font-text-xs-line-height);
}
```

## Control Font Sizes

Font sizes used in form controls and buttons:

| Token | Value |
|-------|-------|
| `--control-font-size-sm` | `var(--font-text-xs-size)` (12px) |
| `--control-font-size-md` | `var(--font-text-sm-size)` (14px) |
| `--control-font-size-lg` | `var(--font-text-md-size)` (16px) |
