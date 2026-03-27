# Slider

> Fine-tune values within a set range

## Usage

```tsx
import { Slider } from "@openai/apps-sdk-ui/components/Slider";
```

```tsx
<div style={{ width: 300 }}>
  <Slider
    label="Example field"
    max={2000}
    min={0}
    onChange={function Xs(){}}
    resetValue={1000}
    step={10}
    unit="ms"
    value={1000}
  />
</div>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| label | Optional label for the slider, which can be a string or React node. `ReactNode` | - |
| min* | The minimum value the slider can have. `number` | - |
| max* | The maximum value the slider can have. `number` | - |
| resetValue | Value that will be offered as a "reset to default" option. `number` | - |
| step* | The step increment between slider values. `number` | - |
| unit | Unit to display next to the slider value (e.g., ms, px). `string` | - |
| disabled | Disables the slider. `boolean` | - |
| value* | The current value of the slider. `number` | - |
| resetTooltip | String that will be displayed in the tooltip. `string` | `"Reset to default"` |
| prefixUnit | Unit to display to the right of the slider value (e.g., $). `string` | - |
| marks | List of marks to display below the slider track. `SliderMark[]` | - |
| trackColor | Color of the slider track. `string` | - |
| rangeColor | Color of the slider progress along the track. `string` | - |
| className | Custom CSS class. `string` | - |
| onChange* | Callback function invoked when the slider value changes. `(value: number) => void` | - |
| onBlur | Focus event handler. `FocusEventHandler<HTMLInputElement>` | - |
| onFocus | Focus event handler. `FocusEventHandler<HTMLInputElement>` | - |

## Examples

### Adding a tooltip

A tooltip can easily be added to the Slider label by providing JSX instead of a simple string.

```tsx
<Slider
  label={(
    <Tooltip content="More details about this field">
      <TriggerDecorator>Example field</TriggerDecorator>
    </Tooltip>
  )}
  max={2000}
  min={0}
  onChange={() => {}}
  resetValue={1000}
  step={10}
  unit="ms"
  value={1000}
/>
```

### Marks

Slider marks can be easily added by passing an array of values to the `marks` prop. Responsive behaviors are handled automatically.

```tsx
<Slider
  value={value}
  onChange={() => {}}
  label="Passing grade"
  min={1}
  max={3}
  step={1}
  marks={[
    { value: 1, label: "Inaccurate" },
    { value: 2, label: "Some inaccuracies" },
    { value: 3, label: "Accurate" },
  ]}
  trackColor="#61C454"
  rangeColor="#EF4146"
/>
```
