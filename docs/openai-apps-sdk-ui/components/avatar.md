# Avatar

> Display user identities with either text, photo, or an icon

## Usage

```tsx
import { Avatar } from "@openai/apps-sdk-ui/components/Avatar";
```

```tsx
<Avatar
  name="Jane"
  size={48}
/>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| name | Name used to display initials from. `string` | `""` |
| size | Size of the avatar's width & height, in pixels. `number` | - |
| className | Class name applied to the avatar. `string` | - |
| overflowCount | Display a formatted count of overflow objects. `number` | - |
| color | Color used for the avatar: `"primary"` \| `"secondary"` \| `"success"` \| `"info"` \| `"discovery"` \| `"danger"` | `"secondary"` |
| variant | Style variant of the avatar: `"soft"` \| `"solid"` | `"soft"` |
| imageUrl | URL of the image to display as the avatar. `string` | - |
| Icon | Icon to render in the avatar circle. `ComponentType<SVGProps<SVGSVGElement>>` | - |
| onClick | Optional click handler, which also enables semantic interactions. `(() => void)` | - |
| onPointerDown | Optional pointer handler, which also enables semantic interactions. `(() => void)` | - |

## Examples

### Text

For text-based avatars, a single initial is displayed based on the `name` prop passed to the component.

```tsx
<Avatar
  name="David"
  size={48}
/>
```

### Image

To display an image avatar, provide an absolute URL to the image with `imageUrl`. Images will have a soft fade entrance once loaded, or fallback to a text display if the image fail to load.

```tsx
<Avatar
  imageUrl="https://gravatar.com/avatar/9531b260b9693f3394bea8646c6ea141ce58fe5a138b7db7729d60a4c5dde552"
  name="Tyler"
  size={48}
/>
```

### Icon

To display an icon avatar, provide an icon to render to the `Icon` prop. The `name` prop is not used in this case, and can be omitted.

```tsx
<Avatar
  Icon={Robot}
  size={48}
/>
```

### Overflow count

To display an overflow avatar, provide a number to the `overflowCount` prop. The number will be automatically formatted and scaled to fit.

```tsx
<Avatar
  overflowCount={9}
  size={48}
/>
```

### Sizing

To size the avatar, pass a number to the `size` property, which will set the width and height in pixels. Text and icon avatars will scale their sizes dynamically based on this value.

```tsx
<Avatar
  name="David"
  size={48}
/>
```

### Colors & variants

You can stylize the display of the avatar using the `color` and `variant` props.

Available colors: `primary`, `secondary`, `success`, `danger`, `info`, `discovery`

Available variants: `soft`, `solid`

### Roundness

By default, avatars are fully rounded. You can override this by passing a Tailwind rounding class to `className`.

```tsx
<Avatar
  className="rounded-lg"
  color="primary"
  name="Acme, co."
  size={48}
  variant="solid"
/>
```

### Interactive

Avatars can be used as interactive elements by passing an `onClick` handler. The avatar will automatically apply semantic and visual interaction styles.

```tsx
<Avatar
  name="Will"
  size={48}
  onClick={saySup}
/>
```
