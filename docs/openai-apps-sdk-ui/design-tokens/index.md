# Design Tokens

> Foundation for consistent styling across the design system

Design tokens are the atomic values that define the visual language of Apps SDK UI. They are organized into three layers:

1. **Primitive tokens** - Raw color values, alpha transparencies, and base measurements
2. **Semantic tokens** - Contextual values for typography, spacing, borders, and surfaces
3. **Component tokens** - Specific values for individual components

## Token Files

| File | Description |
|------|-------------|
| `variables-primitive.css` | Base color palettes, alpha values, shadows |
| `variables-semantic.css` | Typography, spacing, control sizes, motion, surfaces |
| `variables-components.css` | Component-specific tokens |

## Usage

Tokens are available as CSS custom properties and can be used directly in your styles:

```css
.my-element {
  color: var(--color-text);
  background: var(--color-surface);
  border-radius: var(--radius-md);
  padding: var(--spacing);
}
```

## Theme Support

Tokens automatically adapt to light and dark themes via the `data-theme` attribute:

```html
<!-- Light theme (default) -->
<html data-theme="light">

<!-- Dark theme -->
<html data-theme="dark">
```

## Documentation

- [Colors](./colors.md) - Color palettes and semantic color tokens
- [Typography](./typography.md) - Font families, sizes, weights, and line heights
- [Spacing & Sizing](./spacing.md) - Spacing scale, control sizes, and radius
- [Shadows & Elevation](./shadows.md) - Shadow tokens and elevation levels
- [Motion](./motion.md) - Animation timing functions and durations
