# Textarea

> Semantic multi-line text input collection

## Usage

```tsx
import { Textarea } from "@openai/apps-sdk-ui/components/Textarea";
```

```tsx
<div className="w-[400px]">
  <Textarea
    autoResize
    placeholder="Enter text..."
    rows={3}
  />
</div>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| placeholder | Placeholder text. `string` | - |
| allowAutofillExtensions | Allow autofill extensions to appear in the textarea. `boolean` | `false` |
| disabled | Disables the textarea visually and from interactions. `boolean` | `false` |
| invalid | Mark the textarea as invalid. `boolean` | `false` |
| rows | Default number of rows to display. `number` | `3` |
| autoResize | Automatically adjust the height of the textarea based on its contents. `boolean` | `false` |
| variant | Visual style of the textarea. `"soft"` \| `"outline"` | `"outline"` |
| size | Controls the size of the textarea. `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| gutterSize | Controls gutter on the edges of the textarea, defaults to value from size. `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` | - |
| autoSelect | Select all contents of the textarea when mounted. `boolean` | `false` |
| onAutofill | Callback invoked when the textarea is autofilled by the browser. `(() => void)` | - |
| maxRows | Maximum number of rows that can be displayed when autoResize is enabled. `number` | `Math.max(rows, 10)` |

## Examples

### Variants

Use `variant` to stylize the textarea.

```tsx
// outline
<Textarea placeholder="Enter text..." variant="outline" />

// soft
<Textarea placeholder="Enter text..." variant="soft" />
```

### Auto resize

Enable `autoResize` to automatically grow/shrink the textarea as the user types. Control the bounds with `rows` (initial height) and `maxRows`.

```tsx
<div className="w-[400px]">
  <Textarea
    autoResize
    maxRows={8}
    onChange={function Xs(){}}
    placeholder="Type to grow..."
    rows={3}
    value="Line 1
Line 2
Line 3"
  />
</div>
```

### Sizing

Sizing of the textarea is controlled with `size` and `gutterSize` props. `size` sets the textarea to a specific control height for single-line equivalent, and `gutterSize` sets the horizontal padding.

Each size provides default values for `gutterSize`, as well as font-size and border-radius. Each of these values can be overridden independently.
