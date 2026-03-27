# Select

> Choose from a dropdown of options

## Usage

```tsx
import { Select } from "@openai/apps-sdk-ui/components/Select";
```

```tsx
<Select
  value={fruit}
  options={fruits}
  onChange={handleChange}
  placeholder="Select a fruit..."
  variant="solid"
/>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| onChange* | Callback when selection changes. `CallbackWithOption<T>` \| `CallbackWithOptions<T>` | - |
| options* | Available options. `Options<T>` | - |
| value* | Selected value(s). `string` \| `string[]` | - |
| actions | Actions to display below the options list. `Actions` | - |
| align | The preferred alignment against the trigger. May change when collisions occur. `"start"` \| `"end"` \| `"center"` | `"center"` |
| alignOffset | An offset in pixels from the "start" or "end" alignment options. `number` | `0` |
| block | Extends select to 100% of available width. `boolean` | `true` |
| clearable | Display a clear action that allows the select to be unset. `boolean` | `false` |
| disabled | Disables the select visually and from interactions. `boolean` | `false` |
| dropdownIconType | Icon displayed in the far right of the select trigger. `"none"` \| `"chevronDown"` \| `"dropdown"` | `"dropdown"` |
| id | Allows the select to be targeted with htmlFor. `string` | - |
| listMaxWidth | Defines the max-width property of the custom select menu, in pixels. `number` \| `"auto"` | `auto` |
| listMinWidth | Defines the min-width property of the custom select menu, in pixels. `number` \| `"auto"` | `auto` |
| listWidth | Set the width of the custom select menu. `number` \| `"auto"` | `auto` |
| loading | Displays loading indicator on top of button contents. `boolean` | `false` |
| loadingPlaceholder | Placeholder text for the select while loading. `string` | `"Loading..."` |
| multiple | Determines if the select should support multiple selection. `boolean` | `false` |
| name | Creates the ability to query the value with `[name="${name}"]`. `string` | - |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the trigger with surrounding content. `"start"` \| `"end"` | - |
| optionClassName | Custom class applied to option containers. `string` | - |
| OptionView | Customize the rendered output of individual options. Must be passed as a stable reference. `FC<T>` | - |
| pill | Determines if the select trigger should be a fully rounded pill shape. `boolean` | `false` |
| placeholder | Placeholder text for the select. `string` | `"Select..."` |
| required | Marks the select as a required field when using native form submission. `boolean` | - |
| searchEmptyMessage | Message displayed when search results are empty. Can be a simple string, or custom JSX. `ReactNode` | - |
| searchPlaceholder | Placeholder of the search input. `string` | - |
| searchPredicate | Predicate used to filter searches. `SearchPredicate<T>` | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur. `"top"` \| `"bottom"` | `"bottom"` |
| size | Controls size of the select trigger, and several other aspects of trigger styling. `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| triggerClassName | Custom class applied to the select trigger. `string` | - |
| TriggerStartIcon | Icon displayed at the start of the select trigger. `ComponentType<SVGProps<SVGSVGElement>>` | - |
| TriggerView | Customize the rendered output of the trigger. Must be passed as a stable reference. `FC<T>` \| `FC<MultiSelectTriggerViewProps<T>>` | - |
| variant | Style variant for the select trigger. `"soft"` \| `"outline"` \| `"ghost"` | `"outline"` |

## Examples

### Custom views

You can fully customize the styling and rendering of select's trigger and options:

- **Trigger** – `triggerClassName`, `TriggerStartIcon`, and `TriggerView`
- **Options** – `optionClassName`, `OptionView`, as well as `description` and `tooltip` fields in options

```tsx
const RoleOptionDescription = ({ children }: { children: React.ReactNode }) => (
  <div className="font-normal text-secondary py-px text-[0.935em] leading-[1.45]">
    {children}
  </div>
);

const roles: Role[] = [
  {
    value: "owner",
    label: "Owner",
    description: (
      <RoleOptionDescription>
        Can modify project information and manage project members
      </RoleOptionDescription>
    ),
  },
  {
    value: "reader",
    label: "Reader",
    description: (
      <RoleOptionDescription>
        Can make API requests that read or modify data
      </RoleOptionDescription>
    ),
  },
];

const CustomSelect = () => (
  <Select
    value={role}
    options={roles}
    placeholder="Select role..."
    align="start"
    listMinWidth={260}
    variant="ghost"
    size="lg"
    onChange={({ value }) => setRole(value)}
    TriggerStartIcon={role === "owner" ? UserLock : User}
    triggerClassName="font-semibold"
    optionClassName="font-semibold"
  />
)
```

### Actions

Custom, arbitrary actions can be displayed below the options list via the `actions` prop.

```tsx
<Select
  value={value}
  onChange={handleChange}
  options={items}
  placeholder="Select..."
  align="start"
  listMinWidth={240}
  triggerClassName="font-semibold"
  actions={[
    {
      id: "create",
      label: "Create project",
      Icon: Plus,
      onSelect: () => {},
    },
    {
      id: "overview",
      label: "Organization overview",
      Icon: Workspace,
      onSelect: () => {},
    },
  ]}
/>
```

### Grouped options

Select supports option groups. All selects are searchable by default, but will only present a searchbox when it makes sense. Currently, this means when there are 15 or more options.

```tsx
const groupedItems = [
  {
    label: "Models",
    options: [
      ...
    ],
    // Custom limits
    optionsLimit: {
      limit: 7,
      label: "Show all models",
    },
  },
  {
    label: "Fine-tunes",
    options: [
      ...
    ],
    // Default
    optionsLimit: {
      limit: 100,
      label: "Show all",
    },
  },
];

const GroupedOptions = () => {
  const [value, setValue] = useState<string>("");

  return (
    <Select
      value={value}
      options={groupedItems}
      onChange={(v) => setValue(v.value)}
      variant="outline"
      size="lg"
      side="bottom"
      listMinWidth={300}
      searchPlaceholder="Select a model..."
      clearable
    />
  );
};
```

### Multiple selection

Multiple selection is supported through the `multiple` property. This changes how `value`, `onChange`, and `TriggerView` are typed, accepting and returning arrays of values.

```tsx
const MultiFruitTriggerView = ({
  values,
  selectedAll,
}: {
  values: { label: string }[];
  selectedAll: boolean;
}) => {
  const displayValue = selectedAll
    ? "All fruits"
    : values.length === 1
    ? values[0].label
    : `${values.length} fruits`;

  return <>{displayValue}</>;
};

const MultiFruitSelect = () => {
  const [fruits, setFruits] = useState<string[]>([]);

  return (
    <Select
      variant="solid"
      placeholder="Select fruits..."
      options={fruitsOptions}
      name="fruits"
      multiple
      clearable
      value={fruits}
      onChange={(values) => {
          setFruits(values.map(({ value }) => value));
      }}
      TriggerView={MultiFruitTriggerView}
    />
  );
};
```
