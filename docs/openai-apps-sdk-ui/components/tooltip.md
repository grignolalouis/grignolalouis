# Tooltip

> Brief and informative hover text

## Usage

```tsx
import { Tooltip } from "@openai/apps-sdk-ui/components/Tooltip";
```

```tsx
<Tooltip
  content="This is additional context that appears when the trigger is hovered or focused"
>
  <Tooltip.TriggerDecorator>
    Simple text with tooltip
  </Tooltip.TriggerDecorator>
</Tooltip>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| content* | The content of the tooltip. If null, the tooltip will not render. `ReactNode` | - |
| compact | Short, 1-3 word tooltips, stylized inversely from normal tooltips. `boolean` | `false` |
| interactive | Indicates that the tooltip has interactive content, and should remain open when hovered. `boolean` | - |
| maxWidth | Defines the max-width of the tooltip content. "none" creates a single-line, naturally sized tooltip. `number` \| `"none"` | `300` |
| forceOpen | Forces the tooltip to remain open or closed. `boolean` | - |
| openDelay | Delay of when the tooltip is shown from first interaction, in milliseconds. `number` | `150` |
| preventUnintentionalClickToClose | Prevents the tooltip from closing when the trigger is clicked right after opening. `true` \| `false` | - |
| align | The preferred alignment against the trigger. May change when collisions occur. `"start"` \| `"end"` \| `"center"` | `"center"` |
| alignOffset | An offset in pixels from the "start" or "end" alignment options. `number` | `0` |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur. `"top"` \| `"right"` \| `"bottom"` \| `"left"` | `"top"` |
| sideOffset | The distance in pixels from the trigger. `number` | `5` |
| gutterSize | Gutter sizing inside the tooltip content. `"sm"` \| `"md"` \| `"lg"` | `"md"` |
| ref | Ref for the tooltip. `Ref<HTMLDivElement \| null>` | - |
| onPointerDown | Pointer event handler. `PointerEventHandler` | - |
| onClick | Click event handler. `MouseEventHandler` | - |
| contentClassName | Optional class name to apply to the tooltip content. `string` | - |

## Examples

### Different triggers

Tooltip provides an optional component, `Tooltip.TriggerDecorator`, to help create accessible tooltip triggers. However, any component can be used as a trigger.

```tsx
<div className="flex items-center gap-4">
  <Tooltip
    content="This is additional context that appears when the trigger is hovered or focused"
  >
    <Button
      color="primary"
      size="lg"
    >
      Sample button
    </Button>
  </Tooltip>
  <Tooltip
    content="This is additional context that appears when the trigger is hovered or focused"
  >
    <span>
      Inaccessible trigger
    </span>
  </Tooltip>
</div>
```

### Conditionally enabled

Sometimes a tooltip should only be disabled under certain conditions, such as when a component is disabled, providing more context as to why that is. Below is an example of how to do this by conditionally passing in null content.

```tsx
<Tooltip
  content={disabled ? "This action is disabled for reasons" : null}
>
  <Button color="primary" size="lg" disabled={disabled}>
    Sample button
  </Button>
</Tooltip>
```
