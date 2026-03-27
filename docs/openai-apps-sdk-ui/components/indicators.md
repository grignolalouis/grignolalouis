# Indicators

> Display loading and progress states to users

## LoadingIndicator

Simple spinning indicator for general loading states.

### Usage

```tsx
import { LoadingIndicator } from "@openai/apps-sdk-ui/components/Indicator";
```

```tsx
<LoadingIndicator size={24} />
```

### Reference

| Name | Description | Default |
|------|-------------|---------|
| size | Size of the indicator, in pixels. `string` \| `number` | `1em` |
| className | Classname applied to the indicator. `string` | - |
| strokeWidth | Stroke width of the indicator, in pixels. `number` | `2` |

### Sizing & stroke

By default, the indicator adapts to the surrounding font-size and color of text.

You can control the size of the LoadingIndicator using the `--indicator-size` CSS custom property.

```tsx
<LoadingIndicator
  size={30}
  strokeWidth={2}
/>
```

### Color

The indicator defaults to `currentcolor`, inheriting the surrounding text color. This can also be customized by altering the `--indicator-color` variable around the DOM scope of the component.

```tsx
<div className="flex items-center gap-2 text-danger">
  <LoadingIndicator />
  Destroying forever...
</div>
```

### Duration

You can control the rotation speed of the spinner with `--indicator-rotate-duration`.

```tsx
<div
  style={{
    '--indicator-rotate-duration': '3s'
  }}
>
  <LoadingIndicator />
</div>
```

---

## CircularProgress

Circular progress ring with simulated progress animation.

### Usage

```tsx
import { CircularProgress } from "@openai/apps-sdk-ui/components/Indicator";
```

```tsx
<CircularProgress />
```

### Reference

| Name | Description | Default |
|------|-------------|---------|
| className | Classname applied to the indicator. `string` | - |
| size | Size of the indicator, in pixels. `string` \| `number` | `1em` |
| strokeWidth | Stroke width of the indicator, in pixels. `number` | `2` |
| progress | Static progress value (0-100). Prevents animation when set. `number` | - |

### Progress

Use `progress` to define a static progress and prevent the animation.

```tsx
<CircularProgress progress={25} />
```

### Sizing & stroke

Use `size` and `strokeWidth` to control the sizing and thickness of the loader.

You can also control these values with CSS variables by targeting `--circular-progress-size` and `--circular-progress-stroke`.

```tsx
<CircularProgress
  size={30}
  strokeWidth={2}
/>
```

### Color

Customize the color of the indicator with the `--circular-progress-track-color` and `--circular-progress-track-active-color` variables.

```tsx
<CircularProgress
  trackActiveColor="var(--gray-1000)"
  trackColor="var(--alpha-15)"
/>
```

---

## LoadingDots

Indicate typing progress with staggered pulsing dot animation.

### Usage

```tsx
import { LoadingDots } from "@openai/apps-sdk-ui/components/Indicator";
```

```tsx
<LoadingDots />
```

### Color

The indicator defaults to `currentcolor`, inheriting the surrounding text color.

You can customize the color by providing a different color value or context.

```tsx
<LoadingDots className="text-danger" />
```
