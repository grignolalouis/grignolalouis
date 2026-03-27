# DatePicker

> Select a single date with an interactive calendar

## Usage

```tsx
import { DatePicker } from "@openai/apps-sdk-ui/components/DatePicker";
```

```tsx
<DatePicker
  value={selectedDate}
  onChange={(nextDate) => {
    setSelectedDate(nextDate);
  }}
  clearable
  pill
/>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| size | Determines size of the size and spacing of the control. `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| pill | Determines if the select trigger should be a fully rounded pill shape. `boolean` | `false` |
| clearable | Display a clear action that allows the select to be unset. `boolean` | `false` |
| id* | Allow targeting the input for forms and accessibility. `string` | - |
| value* | The selected date value. `DateTime<boolean> \| null` | - |
| onChange* | Handler that is triggered when the date changes. `(nextValue: DateTime<boolean> \| null) => void` | - |
| min | Defines the earliest selectable date (inclusive). `DateTime<boolean>` | - |
| max | Defines the latest selectable date (inclusive). `DateTime<boolean>` | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur. `"top"` \| `"right"` \| `"bottom"` \| `"left"` | `"bottom"` |
| sideOffset | The distance in pixels from the trigger. `number` | `8` |
| align | The preferred alignment against the trigger. May change when collisions occur. `"start"` \| `"end"` \| `"center"` | `"center"` |
| alignOffset | An offset in pixels from the "start" or "end" alignment options. `number` | `0` |
| disabled | Disables the select visually and from interactions. `boolean` | `false` |
| placeholder | Placeholder text for the select. `string` | `"Select date..."` |
| variant | Style variant for the select trigger. `"soft"` \| `"outline"` \| `"ghost"` | `"outline"` |
| dropdownIconType | Icon displayed in the far right of the select trigger. `"none"` \| `"chevronDown"` \| `"dropdown"` | `"dropdown"` |
| triggerClassName | Custom class applied to the select trigger. `string` | - |
| triggerShowIcon | Display calendar icon at the start of the trigger. `boolean` | `true` |
| triggerDateFormat* | Format of dates displayed in the trigger. `string` | - |
| block | Extends select to 100% of available width. `boolean` | `true` |

## Examples

### Limits

Use `min` and `max` to limit selectable dates to a specific timeframe.

```tsx
const today = DateTime.local()
const minDate = today.minus({ days: 30 }).startOf("day")
const maxDate = today.plus({ days: 30 }).endOf("day")
const [selectedDate, setSelectedDate] = useState<DateTime | null>(today)

return (
  <DatePicker
    ...
    min={minDate}
    max={maxDate}
  />
)
```

### Without Icon

Remove the calendar icon from the trigger by setting `triggerShowIcon` to `false`.

```tsx
<DatePicker
  ...
  triggerShowIcon={false}
  placeholder="Choose a date"
/>
```

### Disabled

Disable the picker to prevent user interaction.

```tsx
<DatePicker
  ...
  disabled
/>
```
