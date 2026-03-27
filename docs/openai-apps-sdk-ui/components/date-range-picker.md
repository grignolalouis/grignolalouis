# DateRangePicker

> Select a date range with an interactive calendar

## Usage

```tsx
import { DateRangePicker } from "@openai/apps-sdk-ui/components/DateRangePicker";
```

```tsx
<DateRangePicker
  value={selectedDateRange}
  onChange={(nextDateRange) => {
    setSelectedDateRange(nextDateRange);
  }}
  shortcuts={dayShortcuts}
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
| value* | The selected date range value. `DateRange \| null` | - |
| onChange* | Handler that is triggered when the date range changes. `(nextValue: DateRange \| null, shortcut?: DateRangeShortcut \| undefined) => void` | - |
| min | Defines the earliest selectable date (inclusive). `DateTime<boolean>` | - |
| max | Defines the latest selectable date (inclusive). `DateTime<boolean>` | - |
| maxRangeDays | Maximum length of the selectable range in days (inclusive). When set, the end date cannot be more than this many days after the start date. `number` | - |
| shortcuts | List of date range shortcuts displayed for quick selection, shown to the left of the calendar. `DateRangeShortcut[]` | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur. `"top"` \| `"right"` \| `"bottom"` \| `"left"` | `"bottom"` |
| sideOffset | The distance in pixels from the trigger. `number` | `8` |
| align | The preferred alignment against the trigger. May change when collisions occur. `"start"` \| `"end"` \| `"center"` | `"center"` |
| alignOffset | An offset in pixels from the "start" or "end" alignment options. `number` | `0` |
| disabled | Disables the select visually and from interactions. `boolean` | `false` |
| placeholder | Placeholder text for the select. `string` | `"Select date range..."` |
| variant | Style variant for the select trigger. `"soft"` \| `"outline"` \| `"ghost"` | `"outline"` |
| dropdownIconType | Icon displayed in the far right of the select trigger. `"none"` \| `"chevronDown"` \| `"dropdown"` | `"dropdown"` |
| triggerClassName | Custom class applied to the select trigger. `string` | - |
| triggerShowIcon | Display calendar icon at the start of the trigger. `boolean` | `true` |
| triggerStepperUnit | Allows the trigger to display as a stepper when the selected date matches the unit. Currently 'month' is the only supported unit. `"month"` | - |
| triggerDateFormat | Format of dates displayed in the trigger. `string` | `"MM/dd/yy"` |
| block | Extends select to 100% of available width. `boolean` | `true` |

## Examples

### Limits

Use `min` and `max` to limit date ranges to a specific timeframe.

You can also use `maxRangeDays` to limit the range of days allowed.

```tsx
const today = DateTime.local()
const minDate = today.minus({ days: 120 }).startOf("day")
const maxDate = today.endOf("day")
const [selectedDateRange, setSelectedDateRange] = useState<DateRange | null>(() =>
  getMonthStartAndEnd(today, { min: minDate, max: maxDate }),
)

return (
  <DateRangePicker
    ...
    min={minDate}
    max={maxDate}
  />
)
```

### Shortcuts

Use the `shortcuts` array to provide a list of quick data shortcuts.

When a given shortcut is selected, it's label is displayed in the trigger.

```tsx
<DateRangePicker
  ...
  shortcuts={dayShortcuts}
/>
```

### Month stepper

Enable a stepper view in the trigger by passing `stepperUnit`. When the selected date matches the unit (e.g., a month), the trigger view will convert into the stepper view.

When the range does not match the stepper unit, the normal trigger is displayed.

```tsx
<DateRangePicker
  ...
  triggerStepperUnit="month"
/>
```
