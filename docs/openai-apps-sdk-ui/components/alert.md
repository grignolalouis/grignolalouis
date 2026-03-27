# Alert

> Call attention to a specific message or warning

## Usage

```tsx
import { Alert } from "@openai/apps-sdk-ui/components/Alert";
```

```tsx
<Alert
  actions={<Button color="primary" pill variant="soft">Dismiss</Button>}
  description="We'll be offline 2 - 4 AM UTC on July 14 while we upgrade our database."
  title="Scheduled maintenance"
/>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| title | Title displayed in the alert. `ReactNode` | - |
| description | Description text displayed in the alert. `ReactNode` | - |
| actions | Actions associated with the Alert. `ReactNode` | - |
| color | Color for the button: `"primary"` \| `"success"` \| `"info"` \| `"discovery"` \| `"danger"` \| `"warning"` \| `"caution"` | `"primary"` |
| variant | Style variant for the Button: `"soft"` \| `"solid"` \| `"outline"` | `"outline"` |
| actionsPlacement | Sets the placement of actions always on the end or the bottom. Default behavior is automatic placement based on sizing. `"end"` \| `"bottom"` | - |
| indicator | Optional override for the default indicator of the alert. When false, no indicator is shown. `ReactNode` | - |
| className | Class applied to the alert container. `string` | - |
| actionsClassName | Class applied to the actions container. `string` | - |
| ref | Ref applied to the alert container. `Ref<HTMLDivElement>` | - |

## Examples

### Colors & variants

You can stylize the display of the alert using the `color` and `variant` props.

Available colors: `primary`, `success`, `danger`, `warning`, `caution`, `info`, `discovery`

Available variants: `outline`, `soft`, `solid`

### Title

You can optionally include a title for your alert with the `title` prop.

```tsx
<Alert title="Your current access level limits what you can view or modify" />
```

### Description

You can optionally include description text for your alert with the `description` prop.

```tsx
<Alert description={<>We're working on centralizing SCIM and invite settings. For now, setup is handled within individual product settings.{' '}<TextLink href="#">Learn more</TextLink></>} />
```

### Actions

You can add actions to the alert with the `actions` prop, which accepts ReactNode.

```tsx
<Alert
  variant="soft"
  color="warning"
  title="Password expires in 3 days"
  description="Update it now to avoid losing access to your account."
  actions={<Button color="primary" pill>Update password</Button>}
/>
```

### Action placement

Actions are automatically, intelligently positioned in the alert by default.

You can force a specific position with the `actionsPlacement` prop, by passing either `'end'` or `'bottom'`. This would be ideal for long alert messages with multiple actions.

```tsx
<Alert
  title="Our terms of service has been updated"
  description="We've updated our terms to clarify how we handle data, billing, and user permissions. Please review and accept the latest terms to avoid impacting your service."
  actions={(
    <>
      <Button color="primary" pill variant="soft">Set reminder</Button>
      <Button color="primary" pill variant="solid">Review terms</Button>
    </>
  )}
  actionsPlacement="bottom"
/>
```

### Indicator

Alert provides an indicator icon by default, which changes based on the color passed to the component (e.g., success, warning, error).

You can override the default indicator by passing a custom icon to `indicator`.

```tsx
<Alert
  indicator={<Lightbulb />}
  description={(
    <>
      We're working on centralizing SCIM and invite settings. For now, setup is handled within
      individual product settings. <TextLink href="#">Learn more</TextLink>
    </>
  )}
/>
```

To hide the indicator entirely, pass `indicator={false}`.

```tsx
<Alert
  indicator={false}
  description="Version 2.18.5 rolls out behind-the-scenes tweaks to caching and background sync. You don't need to do anything—updates apply automatically the next time you open the app. Most changes are performance-related; if you notice smoother scrolling or slightly faster load times, that's why."
/>
```

### Dismissible

The suggested approach for dismissible notices is to use labeled buttons via `actions`.

```tsx
<Alert
  className="items-start"
  title="Try our new dashboard layout"
  description="We've introduced a streamlined layout that makes using the dashboard even easier. You can switch back any time."
  actions={(
    <>
      <Button color="primary" variant="soft" pill>
        Dismiss
      </Button>
      <Button color="primary" variant="solid" pill>
        Try it
      </Button>
    </>
  )}
/>
```
