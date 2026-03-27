# TextLink

> Semantic link used for both internal and external links

## Usage

```tsx
import { TextLink } from "@openai/apps-sdk-ui/components/TextLink"
```

```tsx
<p>
  You can use the{' '}
  <TextLink href="#">responses endpoint</TextLink>{' '}
  to generate text. You can either use the API directly from an HTTP client of your choice, or use one of OpenAI's{' '}
  <TextLink href="#">official SDKs</TextLink>{' '}
  for your preferred language.
</p>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| href | Link destination. `string` | - |
| primary | Applies a primary color to the link and removes the default underline. `boolean` | `false` |
| underline | Apply text-decoration: underline to the Link. `boolean` | `true` |
| forceExternal | Force external link behavior, which is automatically detected based on the URL. `boolean` | - |
| as | Override the default component used for the link. This is useful for using a routing library, or SSR rendering purposes. `"a"` \| `ComponentType<any>` | `'a'` |

## Examples

### Default inheritance

By default, TextLink uses `currentcolor` inheritance and `text-decoration: underline` to create subtle visual differentiation from surrounding text. The hover effect is a dynamic deemphasis of the currentcolor, with some special cases for `text-secondary` and `text-tertiary` contexts.

```tsx
<p className="text-secondary">
  You can use the{' '}
  <TextLink href="#">
    responses endpoint
  </TextLink>
  {' '}to generate text. You can either use the API directly from an HTTP client of your choice, or use one of OpenAI's{' '}
  <TextLink href="#">
    official SDKs
  </TextLink>
  {' '}for your preferred language.
</p>
```

### Primary color

You can create a colorful link style with the `primary` prop, which uses color for visual differentiation.

Primary links also remove the default underline treatment - pass `underline` re-apply that style.

```tsx
<p>
  Sample text with a{' '}
  <TextLink
    href="#"
    primary
  >
    primary link
  </TextLink>
</p>
```

### Underline

Links have an underlined aesthetic by default.

Pass `underline={false}` to remove the underline from the link.

```tsx
<p className="text-secondary">
  Sample text with a{' '}
  <TextLink
    href="#"
    underline={false}
  >
    subtle link
  </TextLink>
</p>
```

### External links

When external paths are provided, `<a>` will be used with `target="_blank"` and `rel="noopener noreferrer"` included by default. You can also compose icons along with the text to add visual indication.

```tsx
<TextLink primary underline href="https://openai.com">
  External link <ArrowUpRight />
</TextLink>
```

### Font weight

To customize the font weight, pass a Tailwind class to the `className` prop.

```tsx
<TextLink className="font-semibold" underline={false} href="#">
  Contact support <ArrowRight />
</TextLink>
```

### Configure your Router

#### Provider

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
<TextLink to={{ pathname: "/help" }} prefetch="intent">
  Get Help
</TextLink>
```

#### Component-level

You can also pass your Link component to the `as` prop.

```tsx
import {Link} from "next/link"

<TextLink as={Link} href="/dashboard">
  View Dashboard
</TextLink>
```
