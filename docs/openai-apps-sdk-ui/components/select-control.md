# SelectControl

> Customizable select control for use with any type of floating UI

## Usage

```tsx
import { SelectControl } from "@openai/apps-sdk-ui/components/SelectControl";
```

```tsx
const [value, setValue] = useState("")
const placeholder = "Select date..."

return (
  // Use any floating UI, like <Menu>, <Popover>, etc.
  <Menu>
    <Menu.Trigger>
      <SelectControl
        selected={!!value}
        onClearClick={() => setValue("")}
        StartIcon={CalendarAlt}
      >
        {value || placeholder}
      </SelectControl>
    </Menu.Trigger>
    <Menu.Content>
      <Menu.RadioGroup value={value} onChange={setValue}>
        ...
      </Menu.RadioGroup>
    </Menu.Content>
  </Menu>
)
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| variant | Style variant for the Button. `"soft"` \| `"outline"` \| `"ghost"` | `"outline"` |
| pill | Determines if the control should be a fully rounded pill shape. `boolean` | `true` |
| size | Determines size of the size and spacing of the control. `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| block | Extends the control to 100% of available width. `boolean` | `true` |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the control with surrounding content. `"start"` \| `"end"` | - |
| disabled | Disables the control visually and from interactions. `boolean` | `false` |
| invalid | Visually indicates that the control is in an invalid state. `boolean` | `false` |
| selected | Indicates that the control is selected. An unselected state will display placeholder styles. `boolean` | `false` |
| onClearClick | Display a clear action that allows the select to be unset. `(() => void)` | `false` |
| onInteract | Primary handler for when the control is selected with pointer or keyboard events. `(() => void)` | - |
| loading | Displays loading indicator on top of button contents. `boolean` | `false` |
| dropdownIconType | Icon displayed in the far right of the select trigger. `"none"` \| `"chevronDown"` \| `"dropdown"` | `"dropdown"` |
| StartIcon | Icon displayed at the start of the control. `ComponentType<SVGProps<SVGSVGElement>>` | - |
| ref | Reference to the element. `Ref<HTMLSpanElement \| null>` | - |

## Examples

### Variants

Use the `variant` prop to stylize the select control. Available variant styles are similar to `<Button>`, but aligned with subtle differences from `<Input>` variant treatments.

```tsx
// soft
<SelectControl variant="soft">Select...</SelectControl>

// outline
<SelectControl variant="outline">Select...</SelectControl>

// ghost
<SelectControl variant="ghost">Select...</SelectControl>
```

### Sizing & roundness

Sizing of the control is determined with the `size` prop. Each size provides dynamic values for various aspects of the control, including icon and indicator placement, as well font-size and gutter values.

Create fully rounded controls with the `pill` prop. When `pill` is set, extra horizontal gutter is dynamically applied, and the clear action is also set to pill.

```tsx
<SelectControl size="md" pill>
  Select...
</SelectControl>
```

### Selected

Use `selected` to indicate if the control has a selected value, which toggles visual placeholder styling.

As you'll notice here, this doesn't do anything to the content of the control – that's up to you.

```tsx
<SelectControl selected>
  Select...
</SelectControl>
```

### Start icon

Use `StartIcon` to display an icon in the control. Sizing, spacing, and coloring are handled automatically.

```tsx
<SelectControl StartIcon={CalendarAlt}>
  Reader
</SelectControl>
```

### Dropdown icon

Use `dropdownIconType` to control the presentation of the dropdown indicator.

```tsx
<SelectControl dropdownIconType="dropdown">
  Select...
</SelectControl>
```

### Clearable

Pass a callback `onClearClick` to enable the clearable action.

```tsx
<SelectControl
  onClearClick={function Xs(){}}
  onInteract={function Xs(){}}
  selected
>
  Sample value
</SelectControl>
```

### Loading

During loading, dropdown icon and clear actions are automatically hidden.

Interactions will be prevented by default during this state, by providing a default value for `inert` to `true`. You can override this behavior directly with `inert`, or use `disabled` to add visual disablement.

```tsx
<SelectControl loading>
  Loading models...
</SelectControl>
```

### Invalid

Use `invalid` to visually indicate the control is in an invalid state.

```tsx
<SelectControl invalid>
  Pineapple on pizza
</SelectControl>
```

### Disabled

Use `disabled` to both visually and accessibly disable the control.

```tsx
<SelectControl disabled>
  Reader
</SelectControl>
```

### Block

Create full-width controls with the `block` prop.

```tsx
<div className="w-[290px] text-center p-2 border border-dashed border-alpha/20 rounded-md">
  <SelectControl
    block
    size="lg"
  >
    Select...
  </SelectControl>
</div>
```

### Optical alignment

Use `opticallyAlign` with either `"start"` or `"end"` to offset the gutter of the control.

```tsx
// Default
<SelectControl>Select...</SelectControl>

// opticallyAlign="start"
<SelectControl opticallyAlign="start">Select...</SelectControl>
```
