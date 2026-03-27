# Switch

> Toggle control for on and off states

## Usage

```tsx
import { Switch } from "@openai/apps-sdk-ui/components/Switch";
```

```tsx
<Switch />
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| id | The id of the switch. `string` | - |
| defaultChecked | The state of the switch when it is initially rendered. Use when you do not need to control its state. `boolean` | - |
| checked | The controlled state of the switch. Must be used in conjunction with onCheckedChange. `boolean` | - |
| label | Optional accessible label rendered to the right of the checkbox. `ReactNode` | - |
| onCheckedChange | Event handler called when the state of the switch changes. `((nextState: boolean) => void)` | - |
| onBlur | Event handler called when the checkbox looses focus. `FocusEventHandler<HTMLButtonElement>` | - |
| onFocus | Event handler called when the checkbox gains focus. `FocusEventHandler<HTMLButtonElement>` | - |
| disabled | When true, prevents the user from interacting with the switch. `boolean` | - |
| required | When true, indicates that the user must check the switch before the owning form can be submitted. `boolean` | - |
| name | The name of the switch. Submitted with its owning form as part of a name/value pair. `string` | - |
| value | The value given as data when submitted with a name. `string` | - |
| className | CSS classes applied to wrapper node. `string` | - |
| labelPosition | The position of the label relative to the switch. `"start"` \| `"end"` | `"end"` |

## Examples

### With label

You can add a label to the component by using the `label` prop. The label will automatically connect to the switch with `id`.

```tsx
<Switch label="Notifications" />
```

### Label position

Set `labelPosition="start"` to place the label on the left side of the switch control.

```tsx
<Switch
  label="Right aligned"
  labelPosition="start"
/>
```

### Default checked

Initialize the switch with `defaultChecked` when you don't need to control its state. You can then use the `name` prop to read the value later on.

```tsx
<Switch
  defaultChecked
  name="field-set-as-default"
/>
```

### Controlled

Pass `checked` and `onCheckedChange` to manage the state in a controlled manner.

```tsx
const [checked, setChecked] = useState(false)

<Switch checked={checked} onCheckedChange={setChecked} />
```

### Disabled

Use `disabled` to prevent the user from toggling the control.

```tsx
<div className="flex gap-6">
  <Switch disabled />
  <Switch
    checked
    disabled
  />
</div>
```
