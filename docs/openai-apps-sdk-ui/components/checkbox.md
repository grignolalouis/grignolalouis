# Checkbox

> Toggle control for on and off states

## Usage

```tsx
import { Checkbox } from "@openai/apps-sdk-ui/components/Checkbox";
```

```tsx
<Checkbox
  label="Same as billing address"
/>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| disabled | When true, prevents the user from interacting with the checkbox. `boolean` | - |
| defaultChecked | The state of the checkbox when it is initially rendered. Use when you do not need to control its state. `boolean` \| `"indeterminate"` | - |
| label | Optional accessible label rendered to the right of the checkbox. `ReactNode` | - |
| id | The id of the checkbox. `string` | - |
| checked | The controlled state of the checkbox. Must be used in conjunction with onCheckedChange. `boolean` \| `"indeterminate"` | - |
| onCheckedChange | Event handler called when the state of the checkbox changes. `((nextState: boolean) => void)` | - |
| onBlur | Event handler called when the checkbox looses focus. `FocusEventHandler<HTMLButtonElement>` | - |
| onFocus | Event handler called when the checkbox gains focus. `FocusEventHandler<HTMLButtonElement>` | - |
| required | When true, indicates that the user must check the checkbox before the owning form can be submitted. `boolean` | - |
| name | The name of the checkbox. Submitted with its owning form as part of a name/value pair. `string` | - |
| value | The value given as data when submitted with a name. `string` | - |
| className | CSS classes applied to wrapper node. `string` | - |
| orientation | The orientation of the checkbox relative to the label. `"right"` \| `"left"` | `"left"` |

## Examples

### Indeterminate

Use `checked="indeterminate"` to indicate that the checkbox is partially selected.

```tsx
<Checkbox
  checked="indeterminate"
/>
```
