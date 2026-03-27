# CopyTooltip

> Allow users to easily copy to clipboard

## Usage

```tsx
import { CopyTooltip } from "@openai/apps-sdk-ui/components/Tooltip";
```

```tsx
<CopyTooltip copyValue="Very cool content to copy">
  <Tooltip.TriggerDecorator>
    sess_12345abcdefg
  </Tooltip.TriggerDecorator>
</CopyTooltip>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| copyValue* | Value to copy to the clipboard. `string` | - |
| openDelay | Delay of when the tooltip is shown from first interaction, in milliseconds. `number` | `150` |
| align | The preferred alignment against the trigger. May change when collisions occur. `"start"` \| `"end"` \| `"center"` | `"center"` |
| alignOffset | An offset in pixels from the "start" or "end" alignment options. `number` | `0` |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur. `"top"` \| `"right"` \| `"bottom"` \| `"left"` | `"top"` |
| sideOffset | The distance in pixels from the trigger. `number` | `5` |
