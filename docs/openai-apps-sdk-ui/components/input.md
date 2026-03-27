# Input

> Semantic input text collection

## Usage

```tsx
import { Input } from "@openai/apps-sdk-ui/components/Input";
```

```tsx
<Input
  placeholder="Enter text..."
/>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| placeholder | Placeholder text. `string` | - |
| allowAutofillExtensions | Allow autofill extensions to appear in the input. `boolean` | `false` |
| disabled | Disables the select visually and from interactions. `boolean` | `false` |
| invalid | Mark the input as invalid. `boolean` | `false` |
| variant | Visual style of the input. `"soft"` \| `"outline"` | `"outline"` |
| size | Controls the size of the input. `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| gutterSize | Controls gutter on the edges of the input, defaults to value from size. `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` | - |
| autoSelect | Select all contents of the input when mounted. `boolean` | `false` |
| onAutofill | Callback invoked when the input is autofilled by the browser. `(() => void)` | - |
| startAdornment | Content rendered at the start of the input. `ReactNode` | - |
| endAdornment | Content rendered at the end of the input. `ReactNode` | - |
| pill | Determines if the button should be a fully rounded pill shape. `boolean` | `false` |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the input with surrounding content. `"start"` \| `"end"` | - |

## Examples

### Variants

Use `variant` to stylize the input.

```tsx
// outline
<Input placeholder="Enter text..." variant="outline" />

// soft
<Input placeholder="Enter text..." variant="soft" />
```

### Sizing & roundness

Sizing of the input is controlled with `size` and `gutterSize` props. `size` sets the input to a specific control height, and `gutterSize` sets the horizontal padding.

Each size provides default values for `gutterSize`, as well as font-size. Each of these values can be overridden independently.

```tsx
<Input placeholder="Enter text..." size="lg" pill />
```

### Start adornment

You can add arbitrary content to the beginning of an input with `startAdornment` – like a search icon.

Ideally, the spacing will look pretty good by default. If you need to customize the spacing:

- `gutterSize` determines the amount of spacing on the edges of the container, which you can fine-tune as needed.
- If you need precise spacing not supported by `gutterSize`, use negative left margin on your adornment directly (e.g., `-ml-2`).
- The spacing between the adornment and the input is controlled with gap on the container, which you can customize as needed with Tailwind classes.

```tsx
<Input
  placeholder="Start adornment"
  startAdornment={<Search className="fill-tertiary" />}
/>
```

### End adornment

You can add arbitrary content to the end of an input with `endAdornment` – like a clear button.

The same spacing guidance from `startAdornment` applies here.

End adornments are most commonly actions that are tucked tightly into the container frame. In these cases, you'll likely reach for negative right margin (e.g., `-mr-2.5`) to achieve that aesthetic.

```tsx
<Input
  placeholder="Enter text..."
  value={value}
  onChange={(evt) => setValue(evt.target.value)}
  pill
  endAdornment={
    value ? (
      <Button
        className="-mr-2.5"
        color="secondary"
        variant="soft"
        uniform
        size="3xs"
        onClick={() => setValue("")}
        pill
      >
        <X />
      </Button>
    ) : undefined
  }
/>
```

### Disabled

Use the `disabled` prop to disable the input, greying it out and preventing user interactions.

```tsx
<Input
  defaultValue="Jane Doe"
  disabled
  placeholder="Enter text..."
/>
```

### Invalid

Use the `invalid` prop to mark the input as invalid. You decide how this state is removed, whether that's through `onFocus`, `onChange`, an `onSubmit` handler, etc.

Default visual styles will be applied, based on the variant. Additionally, `[data-invalid]` is applied to the container for custom styling.

```tsx
<Input
  invalid
  placeholder="Invalid input"
/>
```

### Auto select text

Pass `autoSelect` to select all text in the input – useful when pairing with other copy actions. This prop behaves like an imperative action when toggled and allows selection to change.

```tsx
<Input
  defaultValue="Toggle to auto select"
  placeholder="Add text..."
  autoSelect
/>
```

### Autofill extensions

By default, autofill extensions are prevented by Input. For the occasions where you want browser extensions to be present, pass `allowAutofillExtensions` to remove the disabling.

When `name` is passed, or `type` is set to `"password"`, this value will default to `true`.

```tsx
<Input
  allowAutofillExtensions
  name="email"
  placeholder="Allowed"
/>
```

### With button

You can pair Input and Button components together by using the same `size` value.

```tsx
<div className="flex gap-2">
  <Input
    placeholder="jane.doe@gmail.com"
    size="lg"
    variant="outline"
  />
  <Button
    color="primary"
    size="lg"
    variant="outline"
  >
    Subscribe
  </Button>
</div>
```

### Optical alignment

Use `opticallyAlign` with either `"start"` or `"end"` to offset the gutter of the input.

```tsx
// Default
<Input placeholder="Sample input" />

// opticallyAlign="start"
<Input placeholder="Sample input" opticallyAlign="start" />
```
