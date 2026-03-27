# AvatarGroup

> Display avatars as a single stack

## Usage

```tsx
import { AvatarGroup } from "@openai/apps-sdk-ui/components/Avatar";
```

```tsx
<AvatarGroup size={42}>
  <Avatar name="Tyler" imageUrl="https://gravatar.com/avatar/xyz" />
  <Avatar name="Jane" color="primary" variant="solid" />
  <Avatar name="Tech support" Icon={Robot} variant="solid" />
  <Avatar overflowCount={5} />
</AvatarGroup>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| stack | Determines stacking layer order: `"start"` \| `"end"` | `"start"` |
| size | Size all avatars in the group, in pixels. `number` | - |
| className | Class name passed to the group container. `string` | - |

## Examples

### Stacking direction

You can control the stacking direction using the `stack` prop, as either `"start"` or `"end"`.

### Group sizing

You can control the size of all avatars in the group by passing `size` directly to the `<AvatarGroup>` component.

```tsx
<AvatarGroup
  size={48}
  stack="start"
>
  <Avatar
    color="info"
    name="Tyler"
  />
  <Avatar
    color="discovery"
    name="Jane"
  />
  <Avatar
    color="danger"
    name="Will"
  />
  <Avatar overflowCount={5} />
</AvatarGroup>
```
