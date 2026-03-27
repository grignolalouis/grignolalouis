# ButtonLink

> `<Button>` as a semantic anchor element

## Usage

```tsx
import { ButtonLink } from "@openai/apps-sdk-ui/components/Button";
```

```tsx
<ButtonLink
  color="primary"
  href="https://platform.openai.com"
>
  View API Keys
  <ArrowRight />
</ButtonLink>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| children | Content rendered inside of the Button. `ReactNode` | - |
| color | Color for the button. `string` | `"secondary"` |
| size | Controls size of the button: `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` \| `"3xl"` | `"md"` |
| href | `string` | - |
| block | Determines if the button should take up 100% of available width. `boolean` | `false` |
| disabled | Disables the button visually and from interactions. `boolean` | `false` |
| pill | Determines if the button should be a fully rounded pill shape. `boolean` | `true` |
| className | Custom class applied to the Button element. `string` | - |
| variant | Style variant for the Button: `"soft"` \| `"solid"` \| `"outline"` \| `"ghost"` | `"solid"` |
| disabledTone | Controls the visual tone when the button is disabled. `"relaxed"` will use a default cursor instead of not-allowed. | - |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the button with surrounding content: `"start"` \| `"end"` | - |
| iconSize | Controls the size of icons within the button: `"sm"` \| `"md"` \| `"lg"` \| `"xl"` \| `"2xl"` | - |
| gutterSize | Controls gutter on the edges of the button: `"3xs"` \| `"2xs"` \| `"xs"` \| `"sm"` \| `"md"` \| `"lg"` \| `"xl"` | - |
| external | Explicity specify that the link is an external link. `boolean` | - |
| as | Override the default component used for the link. `"a"` \| `ComponentType<any>` | `'a'` |

## Examples

### Internal link

When a relative `href` or `to` is provided, ButtonLink automatically uses the configured `LinkComponent` from `AppsSDKUIProvider` so your router handles navigation and prefetching.

```tsx
<ButtonLink href="/some-path" color="primary">
  Internal link <ArrowRight />
</ButtonLink>
```

### External link

When linking to an external URL (or when `external` is set), `<a>` is used with `target="_blank"` and `rel="noopener noreferrer"` added automatically.

If your link is not being automatically identified, you can force external link behavior with the `external` prop.

```tsx
<ButtonLink href="https://openai.com" color="primary">
  External link <ArrowUpRight />
</ButtonLink>
```

### Colors & variants

You can stylize the display of the link using the `color` and `variant` props.

Available colors: `primary`, `secondary`, `danger`, `info`, `discovery`, `success`, `caution`, `warning`

Available variants: `soft`, `solid`, `outline`, `ghost`

### Sizing & roundness

Sizing of the link is controlled with `size` and `gutterSize` props. `size` sets the control height, and `gutterSize` sets the horizontal padding.

Create fully rounded links with the `pill` prop. When `pill` is set, extra horizontal gutter is dynamically applied to the link.

### Icons

Icon sizing is controlled by the `iconSize` prop, which makes it easy to add icons as children without additional props.

`size` will provide a default value for `iconSize`, but setting the prop will force the specified size.

```tsx
<ButtonLink
  color="info"
  href="https://platform.openai.com"
  size="lg"
  variant="soft"
>
  <Globe />
  {' '}View website
</ButtonLink>
```

### Block

Create full-width links with the `block` prop.

```tsx
<div className="w-[290px] text-center p-2 border border-dashed border-alpha/20 rounded-md">
  <ButtonLink
    as="a"
    block
    color="primary"
    href="https://platform.openai.com"
    size="lg"
  >
    Continue to dashboard
  </ButtonLink>
</div>
```

### Disabled

Use `disabled` to both visually and accessibly disable a link. The component renders as a `span[role="link"]`, and onClick handles are not bound.

```tsx
<ButtonLink
  href="https://platform.openai.com"
  color="primary"
  disabled
  onClick={alertMsg}
>
  <Key />
  View API Keys
</ButtonLink>
```

## Configure your Router

### Provider

```tsx
// In the root of your App
import {AppsSDKUIProvider} from "@openai/apps-sdk-ui/components/AppsSDKUIProvider"
import {Link} from "react-router"

// Set up types
declare global {
  interface AppsSDKUIConfig {
    LinkComponent: typeof Link
  }
}

// Wrap your app in AppsSDKUIProvider and pass in your router's Link component.
export function App() {
  return (
    <AppsSDKUIProvider linkComponent={Link}>
      {/* other providers... */}
    </AppsSDKUIProvider>
  )
}

// elsewhere - everything just works!
<ButtonLink to={{ pathname: "/help" }} prefetch="intent">
  Get Help
</ButtonLink>
```

### Component-level

You can also pass your Link component to the `as` prop.

```tsx
import {Link} from "next/link"

<ButtonLink as={Link} href="/dashboard">
  View Dashboard
</ButtonLink>
```
