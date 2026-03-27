# TagInput

> Enter multiple unique tags

## Usage

```tsx
import { TagInput } from "@openai/apps-sdk-ui/components/TagInput";
```

```tsx
<div style={{ width: 350 }}>
  <TagInput
    autoFocus
    placeholder="example@openai.com"
    rows={3}
    validator={function Xs(){}}
  />
</div>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| placeholder | Placeholder text for the input. `string` | - |
| validator | A function that returns whether a given value is a valid tag. Invalid tags are highlighted in red. Tags are evaluated for validity only on creation; changing the validator function later has no effect. `((value: string) => boolean)` | - |
| rows | The minimum number of rows for the tag input. `number` | `1` |
| autoFocus | Whether to focus this input on mount. `boolean` | `false` |
| defaultValue | The state of the tag input when it is initially rendered, used when uncontrolled. `Tag[]` | - |
| value | The value of the tag input, used to control the tag input. `Tag[]` | - |
| id | Allows the tag input to be targeted with htmlFor. `string` | - |
| size | Corresponds with Input height when rows=1. `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"xl"` |
| onChange | Callback function invoked when the tag list changes. `((tags: Tag[]) => void)` | - |
| maxTags | The maximum number of tags allowed before the input is disabled; displays a counter below the input. `number` | - |
| delimiters | Controls what characters will count towards creating a new tag. `string[]` | `[',', ' ']` |
| disabled | Disables the tag input visually and from interactions. `boolean` | - |
