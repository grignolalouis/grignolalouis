# SegmentedControl

> Toggle through grouped options

## Usage

```tsx
import { SegmentedControl } from "@openai/apps-sdk-ui/components/SegmentedControl";
```

```tsx
<SegmentedControl
  aria-label="Select view"
  onChange={function Xs(){}}
  value="all"
>
  <SegmentedControl.Option value="all">
    All
  </SegmentedControl.Option>
  <SegmentedControl.Option value="failed">
    Failed
  </SegmentedControl.Option>
  <SegmentedControl.Option value="successful">
    Successful
  </SegmentedControl.Option>
</SegmentedControl>
```

## Reference

### SegmentedControl

| Name | Description | Default |
|------|-------------|---------|
| value* | Controlled value for the group. `string` | - |
| onChange | Callback for when a new value is selected. `((nextValue: T) => void)` | - |
| onClick | Callback any time the control is clicked (even if a new value was not selected). `(() => void)` | - |
| aria-label* | Text read aloud to screen readers when the control is focused. `string` | - |
| size | Controls the size of the segmented control. `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| gutterSize | Controls gutter on the edges of the button, defaults to value from size. `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` | - |
| disabled | Disable the entire group. `boolean` | - |
| block | Display the control as a block element with equal width segments. `boolean` | `false` |
| pill | Determines if the segment control, and its options, should be a fully rounded pill shape. `boolean` | `true` |
| className | Custom CSS class. `string` | - |

### SegmentedControl.Option

| Name | Description | Default |
|------|-------------|---------|
| value* | Option value. `string` | - |
| aria-label | Text read aloud to screen readers when the option is focused. `string` | - |
| children* | Content to render in the option. `ReactNode` | - |
| disabled | Disable the individual option. `boolean` | - |

## Examples

### Sizing & roundness

Sizing of the control is controlled with `size` and `gutterSize` props. `size` sets the control to a specific height, and `gutterSize` sets the horizontal padding of the inner options.

Each size provides default values for `gutterSize`, as well as font-size and border-radius. Each of these values can be overridden independently.

Create a fully rounded control with the `pill` prop. When `pill` is set, extra horizontal gutter is dynamically applied to the inner options.

```tsx
<SegmentedControl size="xl" pill>
  <SegmentedControl.Option value="all">All</SegmentedControl.Option>
  <SegmentedControl.Option value="failed">Failed</SegmentedControl.Option>
  <SegmentedControl.Option value="successful">Successful</SegmentedControl.Option>
</SegmentedControl>
```

### Block

Create full-width controls with the `block` prop.

```tsx
<SegmentedControl block>
  <SegmentedControl.Option value="all">All</SegmentedControl.Option>
  <SegmentedControl.Option value="failed">Failed</SegmentedControl.Option>
  <SegmentedControl.Option value="successful">Successful</SegmentedControl.Option>
</SegmentedControl>
```

### Disabled group

Use `disabled` on the SegmentedControl root to disable all options.

```tsx
<SegmentedControl disabled>
  <SegmentedControl.Option value="all">All</SegmentedControl.Option>
  <SegmentedControl.Option value="failed">Failed</SegmentedControl.Option>
  <SegmentedControl.Option value="successful">Successful</SegmentedControl.Option>
</SegmentedControl>
```

### Disabled option

Use `disabled` on a given `SegmentedControl.Option` to disable only that option.

```tsx
<SegmentedControl>
  <SegmentedControl.Option value="all">All</SegmentedControl.Option>
  <SegmentedControl.Option value="failed">Failed</SegmentedControl.Option>
  <SegmentedControl.Option value="successful" disabled>Successful</SegmentedControl.Option>
</SegmentedControl>
```

### Scrollable

SegmentedControl can support scrolling, but is not enabled by default.

To create a scrollable segmented control, wrap the component in a simple flex wrapper, which will then cause the control to create inner scrolling when applicable. When scrollable, the selected option will automatically be scrolled into view.

```tsx
<div className="flex">
  <SegmentedControl>
    {...}
  </SegmentedControl>
</div>
```
