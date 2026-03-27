# Badge

> Emphasize details with a status indicator

## Usage

```tsx
import { Badge } from "@openai/apps-sdk-ui/components/Badge";
```

```tsx
<Badge
  color="success"
  size="md"
>
  New
</Badge>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| children* | Content rendered inside the badge. `ReactNode` | - |
| color | Color of the badge, related to its meaning or intent: `"secondary"` \| `"success"` \| `"info"` \| `"discovery"` \| `"danger"` \| `"warning"` | `"secondary"` |
| size | Size scale of the badge: `"sm"` \| `"md"` \| `"lg"` | `"sm"` |
| pill | Determines if the badge should be a fully rounded pill shape. `boolean` | `false` |
| className | Class applied to the badge. `string` | - |
| variant | Visual style of the badge: `"soft"` \| `"solid"` \| `"outline"` | `"soft"` |

## Examples

### Colors & variants

You can stylize the display of the badge using the `color` and `variant` props.

Available colors: `secondary`, `success`, `warning`, `danger`, `info`, `discovery`

Available variants: `soft`, `solid`, `outline`

### Size & roundness

You can control the size and roundness of the badge with `size` and `pill` props. When `pill` is set, extra horizontal gutter is dynamically applied to the badge.

Available sizes: `sm`, `md`, `lg`

### Icon

Content within the badge can be composed, like showing icons. Color, sizing, and spacing adapt by default.

```tsx
<Badge color="warning" size="lg">
  <Beta /> Beta
</Badge>
```

### Loading

In this example, additional gap is added with a Tailwind `gap-1.5` class to provide the appropriate visual spacing.

```tsx
<Badge
  className="gap-1.5"
  color="secondary"
  size="lg"
>
  <LoadingIndicator />
  In progress
</Badge>
```
