# Menu

> Structured actions in a dropdown list

## Usage

```tsx
import { Menu } from "@openai/apps-sdk-ui/components/Menu"
```

```tsx
<Menu>
  <Menu.Trigger>
    <Button color="primary" size="lg" variant="ghost">
      Sample menu <ChevronDown />
    </Button>
  </Menu.Trigger>
  <Menu.Content width={210} minWidth={210}>
    <Menu.Item>
      <p className="font-semibold">Sam Smith</p>
      <p className="text-secondary">sam.smith@gmail.com</p>
    </Menu.Item>
    <Menu.Separator />
    <Menu.Link href="/settings">Your profile</Menu.Link>
    <Menu.Link href="https://openai.com/policies/">Terms & policies</Menu.Link>
    <Menu.Item disabled onSelect={() => {}}>
      Feature flags
    </Menu.Item>
    <Menu.Separator />
    <Menu.Item onSelect={() => {}}>Logout</Menu.Item>
  </Menu.Content>
</Menu>
```

> **Note:** Menu prevents Tab presses from advancing focus. Because of this, Menu isn't suitable for generic popover use-cases – use Popover instead.

## Reference

### Menu

| Name | Description | Default |
|------|-------------|---------|
| forceOpen | Force the menu to remain open or closed. `boolean` | - |
| onOpen | Callback triggered when the modal is opened. `(() => void)` | - |
| onClose | Callback triggered when the modal is closed. `(() => void)` | - |
| modal | When set to true, interaction with outside elements will be disabled and only menu content will be visible to screen readers. `boolean` | `false` |

### Menu.Trigger

Renders the element that toggles the menu open and closed. You can use any interactive element (e.g., a button or icon) as the trigger.

### Menu.Content

Renders the dynamic content for the menu. `Menu.Content` is mounted only while the menu is open.

| Name | Description | Default |
|------|-------------|---------|
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur. `"top"` \| `"right"` \| `"bottom"` \| `"left"` | `"bottom"` |
| sideOffset | The distance in pixels from the trigger. `number` | `4` |
| align | The preferred alignment against the trigger. May change when collisions occur. `"start"` \| `"end"` \| `"center"` | `"center"` |
| alignOffset | An offset in pixels from the "start" or "end" alignment options. `number` | `-6` |
| width | Defines the width property of the content. `number` \| `"auto"` | `auto` |
| minWidth | Defines the min-width property of the content, in pixels. `number` \| `"auto"` | `auto` |
| maxHeight | Defines the max-width property of the content, in pixels. `number` | - |

### Menu.Item

Most common component for rendering menu list items. When `onSelect` is omitted, the item is rendered as non-interactive.

| Name | Description | Default |
|------|-------------|---------|
| className | Custom CSS class. `string` | - |
| onSelect | Callback triggered when the item is pressed. `((event: Event) => void)` | - |
| onClick | Callback triggered when the item is clicked. `MouseEventHandler<HTMLDivElement>` | - |
| disabled | Disables the menu item. `boolean` | - |

### Menu.Link

Renders a menu item as a navigational link. Accepts all props supported by the application's router link component.

### Menu.Separator

Renders a divider between menu items.

| Name | Description | Default |
|------|-------------|---------|
| className | Custom CSS class. `string` | - |

### Menu.Sub

Renders a wrapper for nested submenus within a menu.

| Name | Description | Default |
|------|-------------|---------|
| forceOpen | Force the menu to remain open or closed. `boolean` | - |
| onOpen | Callback triggered when the modal is opened. `(() => void)` | - |
| onClose | Callback triggered when the modal is closed. `(() => void)` | - |

### Menu.SubTrigger

Renders a menu item that toggles its associated submenu. Must be used inside a `Menu.Sub`.

| Name | Description | Default |
|------|-------------|---------|
| className | Custom CSS class. `string` | - |
| disabled | Disables the trigger. `boolean` | - |

### Menu.SubContent

Renders the content panel for a submenu. Must follow a `Menu.SubTrigger` within a `Menu.Sub`.

| Name | Description | Default |
|------|-------------|---------|
| sideOffset | Distance from trigger in pixels. `number` | `4` |
| alignOffset | Offset from alignment in pixels. `number` | `-6` |
| width | Width of content. `number` \| `"auto"` | `auto` |
| minWidth | Minimum width. `number` \| `"auto"` | `auto` |
| maxHeight | Maximum height. `number` | - |

### Menu.CheckboxItem

Renders a menu item with a checkbox indicator.

| Name | Description | Default |
|------|-------------|---------|
| checked | Controlled checked state of the checkbox item. `CheckedState` | - |
| onCheckedChange | Event handler called when the checked state changes. `((checked: boolean) => void)` | - |
| className | Class applied to the checkbox item. `string` | - |
| onSelect | Callback triggered when the checkbox item is pressed. `((event: Event) => void)` | - |
| disabled | Disables the checkbox item. `boolean` | - |
| indicatorPosition | The orientation of the indicator within the checkbox item. `"start"` \| `"end"` | `"end"` |
| indicatorVariant | Visual treatment for the checkbox indicator. `"solid"` \| `"ghost"` | `"solid"` |

### Menu.RadioGroup

Renders a group of radio items in a menu.

| Name | Description | Default |
|------|-------------|---------|
| value* | Controlled value. `string` | - |
| onChange* | Fired when selection changes. `(value: T) => void` | - |
| indicatorPosition | The orientation of the indicator within the radio item. `"start"` \| `"end"` | `"end"` |

### Menu.RadioItem

Renders a menu item with a radio indicator – used inside `Menu.RadioGroup`.

| Name | Description | Default |
|------|-------------|---------|
| value* | Radio item value. `string` | - |
| className | Class applied to the radio item. `string` | - |
| onSelect | Callback triggered when the radio item is pressed. `((event: Event) => void)` | - |
| disabled | Disables the radio item. `boolean` | - |

### Menu.ItemActions

Renders a container for additional actions that appear on the menu item. Automatically handles visibility of the actions based on hover.

| Name | Description | Default |
|------|-------------|---------|
| className | Custom CSS class. `string` | - |

### Menu.ItemAction

Renders an action for use in the hover `Menu.ItemActions` container.

| Name | Description | Default |
|------|-------------|---------|
| onClick* | Click handler. `(evt: MouseEvent<Element, MouseEvent>) => void` | - |

## Examples

### Sizing the menu

- **Natural sizing** – use `minWidth="auto"` to have the menu fit naturally to the size of the content.
- **Fixed size** – use `width` and `minWidth` to set the menu to a fixed size, regardless of content size.
- **Flexible sizing** – `minWidth` can be used by itself to describe a menu that must be a given size, but can grow larger depending on its content.
- **Max sizing** – apply `max-width` to the children of `Menu.Content`.

```tsx
<Menu.Content minWidth="auto">
  <Menu.Item onSelect={handleSelect}>
    <Functions height={16} width={16} /> Function
  </Menu.Item>
  ...
</Menu.Content>
```

### Submenus

Use `Menu.Sub`, `Menu.SubTrigger`, and `Menu.SubContent` to create nested menu items.

```tsx
<Menu>
  <Menu.Trigger>
    <Button color="primary" size="lg" variant="ghost">
      Options <ChevronDown />
    </Button>
  </Menu.Trigger>
  <Menu.Content minWidth={180}>
    <Menu.Item onSelect={() => {}}>Edit</Menu.Item>
    <Menu.Item onSelect={() => {}}>Duplicate</Menu.Item>
    <Menu.Separator />
    <Menu.Sub>
      <Menu.SubTrigger>More</Menu.SubTrigger>
      <Menu.SubContent>
        <Menu.Item onSelect={() => {}}>Move to project…</Menu.Item>
        <Menu.Item onSelect={() => {}}>Move to folder…</Menu.Item>
        <Menu.Separator />
        <Menu.Item onSelect={() => {}}>Advanced options…</Menu.Item>
      </Menu.SubContent>
    </Menu.Sub>
    <Menu.Separator />
    <Menu.Item onSelect={() => {}}>Share</Menu.Item>
    <Menu.Item onSelect={() => {}}>Add to favorites</Menu.Item>
    <Menu.Separator />
    <Menu.Item onSelect={() => {}}>Delete</Menu.Item>
  </Menu.Content>
</Menu>
```

### Checkbox items

You can render selectable menu items with `Menu.CheckboxItem`.

- Use `indicatorPosition` to control whether the indicator appears before or after the content of the item.
- Use `indicatorVariant` to switch between a solid and ghost checkmark indicator.
- Pass `onSelect={(evt) => evt.preventDefault()}` to prevent the menu from closing when selecting.

```tsx
const [settings, setSettings] = useState({
  showGrid: true,
  showLabels: false,
  enableShadows: false,
})

return (
  <Menu>
    <Menu.Trigger>
      <Button variant="ghost" color="primary">
        Checkbox menu <ChevronDown />
      </Button>
    </Menu.Trigger>
    <Menu.Content minWidth={200}>
      <Menu.CheckboxItem
        checked={settings.showGrid}
        onCheckedChange={(checked) => setSettings((s) => ({ ...s, showGrid: checked }))}
        onSelect={(evt) => evt.preventDefault()}
        indicatorPosition="end"
        indicatorVariant="filled"
      >
        Show grid lines
      </Menu.CheckboxItem>
      <Menu.CheckboxItem
        checked={settings.showLabels}
        onCheckedChange={(checked) => setSettings((s) => ({ ...s, showLabels: checked }))}
        onSelect={(evt) => evt.preventDefault()}
        indicatorPosition="end"
        indicatorVariant="filled"
      >
        Display labels
      </Menu.CheckboxItem>
      <Menu.CheckboxItem
        checked={settings.enableShadows}
        onCheckedChange={(checked) => setSettings((s) => ({ ...s, enableShadows: checked }))}
        onSelect={(evt) => evt.preventDefault()}
        indicatorPosition="end"
        indicatorVariant="filled"
      >
        Enable shadows
      </Menu.CheckboxItem>
    </Menu.Content>
  </Menu>
)
```

### Radio items

You can render radio options within a menu with `Menu.RadioGroup` and `Menu.RadioItem`.

- Use `indicatorPosition` to control whether the indicator appears before or after the content of the item.
- Pass `onSelect={(evt) => evt.preventDefault()}` to prevent the menu from closing when selecting.

```tsx
<Menu>
  <Menu.Trigger>
    <Button color="primary" variant="ghost">
      Radio menu <ChevronDown />
    </Button>
  </Menu.Trigger>
  <Menu.Content align="start" minWidth="auto" width="auto">
    <Menu.RadioGroup
      indicatorPosition="end"
      value={value}
      onChange={setValue}
    >
      <Menu.RadioItem value="any">Any time</Menu.RadioItem>
      <Menu.RadioItem value="today">Today</Menu.RadioItem>
      <Menu.RadioItem value="last7d">Last 7 days</Menu.RadioItem>
      <Menu.RadioItem value="last30d">Last 30 days</Menu.RadioItem>
      <Menu.RadioItem value="last3m">Last 3 months</Menu.RadioItem>
    </Menu.RadioGroup>
  </Menu.Content>
</Menu>
```

### Item actions

You can render additional actions on `Menu.Item` by using the `Menu.ItemActions` and `Menu.ItemAction` components. This will render a special set of actions that display when a given item is highlighted.

> **Accessibility note:** These actions are not keyboard accessible due to how Radix Menu works, so these should not be critical actions with no other parity.

```tsx
<Menu.Content>
  <Menu.Item onSelect={handleSelect}>
    <span className="flex-1 truncate">Sample thread title</span>
    <Menu.ItemActions>
      <Menu.ItemAction>
        <Edit />
      </Menu.ItemAction>
      <Menu.ItemAction>
        <Delete />
      </Menu.ItemAction>
    </Menu.ItemActions>
  </Menu.Item>
  ...
</Menu.Content>
```
