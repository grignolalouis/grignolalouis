# Spacing & Sizing

> Spacing scale, control sizes, border radius, and breakpoints

## Base Spacing

| Token | Value |
|-------|-------|
| `--spacing` | `0.25rem` (4px) |

Use multiples of the base spacing with `calc()`:

```css
.element {
  padding: calc(var(--spacing) * 2);  /* 8px */
  margin: calc(var(--spacing) * 4);   /* 16px */
  gap: calc(var(--spacing) * 3);      /* 12px */
}
```

## Border Radius

| Token | Value |
|-------|-------|
| `--radius-2xs` | `0.125rem` (2px) |
| `--radius-xs` | `0.25rem` (4px) |
| `--radius-sm` | `0.375rem` (6px) |
| `--radius-md` | `0.5rem` (8px) |
| `--radius-lg` | `0.625rem` (10px) |
| `--radius-xl` | `0.75rem` (12px) |
| `--radius-2xl` | `1rem` (16px) |
| `--radius-3xl` | `1.25rem` (20px) |
| `--radius-4xl` | `1.5rem` (24px) |
| `--radius-full` | `9999px` |

### Control Radius

Radius tokens for form controls:

| Token | Value |
|-------|-------|
| `--control-radius-sm` | `var(--radius-sm)` (6px) |
| `--control-radius-md` | `var(--radius-md)` (8px) |
| `--control-radius-lg` | `var(--radius-lg)` (10px) |
| `--control-radius-xl` | `var(--radius-xl)` (12px) |

## Control Sizes

Height values for interactive controls (buttons, inputs, selects):

| Token | Value |
|-------|-------|
| `--control-size-3xs` | `1.375rem` (22px) |
| `--control-size-2xs` | `1.5rem` (24px) |
| `--control-size-xs` | `1.625rem` (26px) |
| `--control-size-sm` | `1.75rem` (28px) |
| `--control-size-md` | `2rem` (32px) |
| `--control-size-lg` | `2.25rem` (36px) |
| `--control-size-xl` | `2.5rem` (40px) |
| `--control-size-2xl` | `2.75rem` (44px) |
| `--control-size-3xl` | `3rem` (48px) |

## Control Gutters

Horizontal padding for controls:

| Token | Value |
|-------|-------|
| `--control-gutter-2xs` | `0.375rem` (6px) |
| `--control-gutter-xs` | `0.5rem` (8px) |
| `--control-gutter-sm` | `0.625rem` (10px) |
| `--control-gutter-md` | `0.75rem` (12px) |
| `--control-gutter-lg` | `0.875rem` (14px) |
| `--control-gutter-xl` | `1rem` (16px) |
| `--control-gutter-pill-scaling` | `1.33` |

## Control Icon Sizes

| Token | Value |
|-------|-------|
| `--control-icon-size-xs` | `0.875rem` (14px) |
| `--control-icon-size-sm` | `1rem` (16px) |
| `--control-icon-size-md` | `1.125rem` (18px) |
| `--control-icon-size-lg` | `1.25rem` (20px) |
| `--control-icon-size-xl` | `1.375rem` (22px) |
| `--control-icon-size-2xl` | `1.5rem` (24px) |

## Breakpoints

| Token | Value | Description |
|-------|-------|-------------|
| `--breakpoint-xs` | `380px` | Extra small devices |
| `--breakpoint-sm` | `576px` | Small devices |
| `--breakpoint-md` | `768px` | Medium devices (tablets) |
| `--breakpoint-lg` | `1024px` | Large devices (desktops) |
| `--breakpoint-xl` | `1280px` | Extra large devices |
| `--breakpoint-2xl` | `1536px` | 2X large devices |

### Usage with Media Queries

```css
@media (min-width: 768px) {
  /* Medium screens and up */
}

@media (min-width: 1024px) {
  /* Large screens and up */
}
```

## Hairline

For thin borders on high-DPI displays:

| Token | Value (1x) | Value (1.5x+) |
|-------|------------|---------------|
| `--hairline` | `1px` | `0.5px` |

```css
.thin-border {
  border-width: var(--hairline);
}
```
