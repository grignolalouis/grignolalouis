# Popover

> Generic floating UI utility for contextual actions

## Usage

```tsx
import { Popover } from "@openai/apps-sdk-ui/components/Popover";
```

```tsx
<Popover>
  <Popover.Trigger>
    <Button color="primary">Generate</Button>
  </Popover.Trigger>
  <Popover.Content side="right">
    <Textarea />
    <ActionBar />
  </Popover.Content>
</Popover>
```

## Reference

### Popover

| Name | Description | Default |
|------|-------------|---------|
| open | Sets controlled visibility state. `boolean` | - |
| onOpenChange | Callback invoked when visibility state changes. `((nextState: boolean) => void)` | - |
| showOnHover | Show popover on hover. `boolean` | `false` |
| hoverOpenDelay | Delay before showing on hover, in ms. `number` | `150` |

### Popover.Trigger

Renders the element that toggles the popover. The trigger should be the user's point of interaction for revealing the popup.

### Popover.Content

| Name | Description | Default |
|------|-------------|---------|
| avoidCollisions | Whether to avoid collisions with viewport/scroll containers. `boolean` | `true` |
| width | Set the width of the popover, in pixels. `number` \| `"auto"` | `auto` |
| minWidth | Set the min-width of the popover, in pixels. `number` \| `"auto"` | `300` |
| maxWidth | Set the max-width of the popover, in pixels. `number` | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur. `"top"` \| `"right"` \| `"bottom"` \| `"left"` | `"bottom"` |
| sideOffset | The distance in pixels from the trigger. `number` | `8` |
| align | The preferred alignment against the trigger. May change when collisions occur. `"start"` \| `"end"` \| `"center"` | `"center"` |
| alignOffset | An offset in pixels from the "start" or "end" alignment options. `number` | `0` |
| translucent | Whether the popover surface should be translucent. `boolean` | `false` |
| className | Additional class name to apply to the popover content. `string` | - |
| autoFocus | Auto focus the popover content when it is opened. `boolean` | `true` |

## Examples

### Sizing the popover

The popover can be sized with any combination of `width`, `minWidth`, or `maxWidth`. All popovers default to a `minWidth` of 300px, and a `maxWidth` of Radix's viewport detection.

```tsx
<Popover>
  <Popover.Trigger>
    ...
  </Popover.Trigger>
  <Popover.Content minWidth="auto" side="top">
    ...
  </Popover.Content>
</Popover>
```

### Open on hover

Use `showOnHover` to create popovers that appear on hover and focus events. This should be used sparingly and with clear intention.

By default, hover popovers will not alter the focused element on the page, nor restore focus to the trigger on close. However, if interactive content is present in the popover, and tab is used to navigate into the popover, focus will be restored to the trigger on close.

```tsx
<Popover showOnHover>
  <Popover.Trigger>
    ...
  </Popover.Trigger>
  <Popover.Content>
    ...
  </Popover.Content>
</Popover>
```

### Using the controller

You can access `usePopoverController()` controller context from components within `Popover.Content`. The hook exposes two methods, `close()` and `shake()`. They do exactly what you think they do.

- Attempting to submit an empty form calls the `shake()` method
- After async submission occurs (faked loading state), the `close()` method is called to close the popup imperatively.

```tsx
const Example = () => {
  return (
    <Popover>
      <Popover.Trigger>
        <Button color="primary">Generate</Button>
      </Popover.Trigger>
      <Popover.Content side="right" surface="glass">
        <ControllerForm />
      </Popover.Content>
    </Popover>
  )
}

const ControllerForm = () => {
  const [value, setValue] = useState("")
  const [submitting, setSubmitting] = useState(false)
  const { shake, close } = usePopoverController()

  const handleSubmit = (evt: FormEvent) => {
    evt.preventDefault()

    if (!value) {
      shake()
      return
    }

    setSubmitting(true)
    setTimeout(close, 2000)
  }
  return (
    <form onSubmit={handleSubmit}>
      <Textarea value={value} onChange={setValue} />
      <ActionBar loading={submitting} />
    </form>
  )
}
```

### Nesting

All floating UI components in Apps SDK UI can be infinitely nested by relying on `z-index: auto;` and natural stacking order.

Additionally, `esc` keypresses are handled independently as a stacking order.
