# RadioGroup

> Semantic radio option selection

## Usage

```tsx
import { RadioGroup } from "@/components/ui/RadioGroup";
```

```tsx
const [frequency, setFrequency] = useState("daily");

return (
  <div>
    <h3 className="font-semibold text-sm mb-3">Notification frequency</h3>
    <RadioGroup
      direction="col"
      value={frequency}
      onChange={setFrequency}
      aria-label="Notification frequency"
    >
      <RadioGroup.Item value="daily">Daily</RadioGroup.Item>
      <RadioGroup.Item value="weekly">Weekly</RadioGroup.Item>
      <RadioGroup.Item value="monthly">Monthly</RadioGroup.Item>
      <RadioGroup.Item value="never">Never</RadioGroup.Item>
    </RadioGroup>
  </div>
);
```

## Reference

### RadioGroup

| Name | Description | Default |
|------|-------------|---------|
| disabled | Controls whether the entire radio group is disabled. `boolean` | `false` |
| defaultValue | Default selected value. `string` | - |
| value | Controlled selected value. `string` | - |
| name | Name attribute for form submission. `string` | - |
| onChange | Callback when selection changes. `((value: T) => void)` | - |
| aria-label* | Accessible label for the radio options. `string` | - |
| direction | Determines the layout direction of the radio items. `"row"` \| `"col"` | `"row"` |
| className | Class applied to the radio group container. `string` | - |
| required | Whether selection is required. `boolean` | - |

### RadioGroup.Item

| Name | Description | Default |
|------|-------------|---------|
| value* | Value of this radio option. `string` | - |
| disabled | Determines if a given radio item is disabled. `boolean` | `false` |
| required | Whether this item is required. `boolean` | - |
| block | Display as block element. `boolean` | `false` |
| className | Custom CSS class. `string` | - |

## Examples

### Direction

Use `direction` to control whether the items flow in a column or row. An optimal gap will be dynamically applied based on the orientation.

```tsx
<RadioGroup
  aria-label="Sample options"
  direction="col"
>
  <RadioGroup.Item value="option1">
    Option 1
  </RadioGroup.Item>
  <RadioGroup.Item value="option2">
    Option 2
  </RadioGroup.Item>
  <RadioGroup.Item value="option3">
    Option 3
  </RadioGroup.Item>
</RadioGroup>
```

### Group disabled

Use `disabled` on RadioGroup to disable all radio options.

```tsx
<RadioGroup disabled>
  ...
</RadioGroup>
```

### Item disabled

Use `disabled` on single `RadioGroup.Item` to disable only that option.

```tsx
<RadioGroup>
  <RadioGroup.Item value="option1">Option 1</RadioGroup.Item>
  <RadioGroup.Item value="option2">Option 2</RadioGroup.Item>
  <RadioGroup.Item value="option3" disabled>
    This is long content that will wrap multiple lines to demonstrate how line-height affects rendering of the radio group
  </RadioGroup.Item>
</RadioGroup>
```

### Complex layout

Instrument complex layouts by leveraging component composition and `className` overrides.

```tsx
<RadioGroup
  className="flex-col w-[390px] gap-4"
  onChange={() => {}}
  aria-label="Sample options"
>
  <RadioGroup.Item className="gap-2.5" value="basic">
    <div>
      <h4 className="font-semibold mb-1">Basic Plan</h4>
      <p className="text-secondary text-sm">5 GB storage • Email support • Free</p>
    </div>
  </RadioGroup.Item>
  <hr className="border-default" />
  <RadioGroup.Item className="gap-2.5" value="standard">
    <div>
      <h4 className="font-semibold mb-1">Standard Plan</h4>
      <p className="text-secondary text-sm">100 GB storage • Priority email support • $9.99/m</p>
    </div>
  </RadioGroup.Item>
  <hr className="border-default" />
  <Tooltip
    maxWidth={258}
    content={
      <>
        Contact our <TextLink href="#">support team</TextLink> for more information on enterprise plans.
      </>
    }
    interactive
  >
    <Tooltip.Trigger>
      <RadioGroup.Item className="gap-2.5" value="enterprise" disabled>
        <div>
          <h4 className="font-semibold mb-1">Enterprise Plan</h4>
          <p className="text-secondary text-sm">
            Unlimited storage • 24/7 phone support • Custom pricing
          </p>
        </div>
      </RadioGroup.Item>
    </Tooltip.Trigger>
  </Tooltip>
</RadioGroup>
```
