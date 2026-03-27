# Button

> Create actions in many different styles

## Usage

```tsx
import { Button } from "@openai/apps-sdk-ui/components/Button";
```

```tsx
<Button
  color="primary"
  size="md"
  variant="solid"
>
  Submit
</Button>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| children | Content rendered inside of the Button. `ReactNode` | - |
| variant | Style variant for the Button: `"soft"` \| `"solid"` \| `"outline"` \| `"ghost"` | `"solid"` |
| color | Color for the button: `"primary"` \| `"secondary"` \| `"success"` \| `"info"` \| `"discovery"` \| `"danger"` \| `"warning"` \| `"caution"` | `"secondary"` |
| size | Controls size of the button: `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| pill | Determines if the button should be a fully rounded pill shape. `boolean` | `true` |
| disabled | Disables the button visually and from interactions. `boolean` | `false` |
| disabledTone | Controls the visual tone when the button is disabled. `"relaxed"` will use a default cursor instead of not-allowed. | - |
| block | Determines if the button should take up 100% of available width. `boolean` | `false` |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the button with surrounding content: `"start"` \| `"end"` | - |
| iconSize | Controls the size of icons within the button: `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` | - |
| gutterSize | Controls gutter on the edges of the button: `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` | - |
| className | Custom class applied to the Button element. `string` | - |
| uniform | Determines if the button should have matching width and height, based on the size. `boolean` | `false` |
| selected | Displays selected styles on the button, varying by variant. `boolean` | `false` |
| loading | Displays loading indicator on top of button contents. `boolean` | `false` |
| inert | Determines whether the button should be made inert, without introducing visual change. `boolean` | `false` |
| ref | Ref for the button. `Ref<HTMLButtonElement \| null>` | - |

## Examples

### Colors & variants

You can stylize the display of the button using the `color` and `variant` props.

Available colors: `primary`, `secondary`, `danger`, `info`, `discovery`, `success`, `caution`, `warning`

Available variants: `soft`, `solid`, `outline`, `ghost`

### Sizing & roundness

Sizing of the button is controlled with `size` and `gutterSize` props. `size` sets the button to a specific control height, and `gutterSize` sets the horizontal padding.

Each size provides default values for `gutterSize` and `iconSize` props, as well as font-size. Each of these values can be overridden independently.

Create fully rounded buttons with the `pill` prop. When `pill` is set, extra horizontal gutter is dynamically applied to the button.

### Icons

Icon sizing is controlled by the `iconSize` prop, which makes it easy to add icons as children of button without additional props.

Default values for `iconSize` are provided through the `size` prop, but you can pass the prop directly to change the defaults.

For icon-only buttons, there are two common approaches:

- **Square** – create perfect square icon buttons with the `uniform` prop. When `uniform` is passed, `gutterSize` is ignored. Combine with `pill` to make circular icons.
- **Tighter gutters** – applying a smaller `gutterSize` than `size` can create well-sized, but not exactly square, icon buttons.

```tsx
<Button
  color="secondary"
  size="lg"
  uniform
  variant="ghost"
>
  <PlusLg />
</Button>
```

### Block

Create full-width buttons with the `block` prop.

```tsx
<div className="w-[290px] text-center p-2 border border-dashed border-alpha/20 rounded-md">
  <Button
    block
    size="lg"
  >
    Continue
  </Button>
</div>
```

### Disabled

Use `disabled` to both visually and accessibly disable a button.

```tsx
<Button
  disabled
  onClick={function Xs(){}}
>
  Submit
</Button>
```

### Inert

Use `inert` to accessibly disable a button without any visual changes.

Note: For accessibility reasons, `disabled` is used instead of applying `inert` directly to the button. Visual disablement in the `disabled` prop is applied via `[data-disable]`.

```tsx
<Button
  inert
  onClick={function Xs(){}}
>
  Submit
</Button>
```

### Loading

Use `loading` to display a loading indicator in the button, fading out the current content.

Interactions will be prevented by default during this state, by providing a default value for `inert` to `true`. You can override this behavior directly with `inert`, or use `disabled` to add visual disablement.

```tsx
<Button loading {...restProps} />
```

### Selected

Use `selected` to indicate that a given button is correctly in an open or selected state. The exact visual behavior differs across each variant.

This behavior is automatically configured with components like Menu that apply `[aria-expanded="true"]` or `[data-state="open"]` attributes.

```tsx
<Button selected {...restProps} />
```

### Optical alignment

Use `opticallyAlign` with either `"start"` or `"end"` to offset the gutter of the button.
