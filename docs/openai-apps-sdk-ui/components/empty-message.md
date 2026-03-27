# EmptyMessage

> Gracefully inform users when there's nothing to see

## Usage

```tsx
import { EmptyMessage } from "@openai/apps-sdk-ui/components/EmptyMessage"
```

```tsx
<EmptyMessage>
  <EmptyMessage.Icon>
    <Explore />
  </EmptyMessage.Icon>
  <EmptyMessage.Title>Your evaluations will appear here</EmptyMessage.Title>
  <EmptyMessage.Description>
    Create an evaluation to assess your model's responses
  </EmptyMessage.Description>
  <EmptyMessage.ActionRow>
    <Button color="primary" onClick={() => {}} size="lg">
      <Plus className="mr-[-2px]" />
      Create
    </Button>
  </EmptyMessage.ActionRow>
</EmptyMessage>
```

## Reference

### EmptyMessage

| Name | Description | Default |
|------|-------------|---------|
| className | Custom CSS class. `string` | - |
| fill | Determines how the container fills available space. `"none"` \| `"static"` \| `"absolute"` | `"static"` |

### EmptyMessage.Icon

| Name | Description | Default |
|------|-------------|---------|
| size | Size of the icon. `"sm"` \| `"md"` | `"md"` |
| color | Color of the icon. `"secondary"` \| `"danger"` \| `"warning"` | `"secondary"` |
| className | Custom CSS class. `string` | - |

## Examples

### Error message

The `color` property enables you to display clearer intent with the message, such as showing an error state.

```tsx
<EmptyMessage>
  <EmptyMessage.Icon color="danger">
    <Mic />
  </EmptyMessage.Icon>
  <EmptyMessage.Title color="danger">
    Enable microphone access in your browser's settings.
  </EmptyMessage.Title>
</EmptyMessage>
```

### No results

The components of EmptyMessage are both composable and optional. This example omits the `EmptyMessage.Title` component, using only an icon and description for a simpler message style.

```tsx
<EmptyMessage fill="none">
  <EmptyMessage.Icon size="sm">
    <Search />
  </EmptyMessage.Icon>
  <EmptyMessage.Description>
    No icons found matching <span className="font-semibold">"pizza"</span>
  </EmptyMessage.Description>
</EmptyMessage>
```
