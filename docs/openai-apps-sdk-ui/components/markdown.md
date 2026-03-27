# Markdown

> Render rich formatted content

## Usage

```tsx
import { Markdown } from "@openai/apps-sdk-ui/components/Markdown"
```

```tsx
<Markdown>{markdownContent}</Markdown>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| directives | Custom markdown directives. `MarkdownDirective<any>[]` | - |
| includeMath | Determines if remark-math plugins should be loaded for rendering LaTeX. `boolean` | `false` |
| breakNewLines | Determines whether single newlines should insert `<br>` tags. `boolean` | `false` |
| components | Custom component overrides. `Record<string, MarkdownComponent>` | - |
| remarkPlugins | Additional remark plugins. `PluggableList \| null` | - |
| rehypePlugins | Additional rehype plugins. `PluggableList \| null` | - |
| allowedElements | List of allowed HTML elements. `readonly string[] \| null` | - |
| disallowedElements | List of disallowed HTML elements. `readonly string[] \| null` | - |
| urlTransform | Transform function for URLs. `UrlTransform \| null` | Custom transform for tel/sms URLs |
| skipHtml | Skip rendering raw HTML. `boolean` | - |
| className | Custom CSS class. `string` | - |
| copyableCodeBlocks | Enable copy button on code blocks. `boolean` | `true` |
| children | Markdown content to render. | - |

## Supported Elements

### Headers

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

### Text samples

```markdown
*Emphasis*, aka *italics*, with asterisks or underscores.

**Strong emphasis**, aka **bold**, with asterisks or underscores.

***Combined emphasis*** with asterisks and underscores.

~~Strikethrough~~ uses two tildes. Scratch this.
```

### Lists

**Unordered List:**
```markdown
- Item 1
- Item 2
  - Nested Item 1
  - Nested Item 2
```

**Ordered List:**
```markdown
1. First item
2. Second item
   1. Subitem 1
   2. Subitem 2
```

### Blockquote

```markdown
> This is a blockquote.
>
> It can span multiple lines and include other elements like lists or even code.
```

### Table

```markdown
| ID | Title | Owner | Updated | Progress |
|----|-------|-------|---------|----------|
| UX-17 | Notebook typography polish | Tyler | 2025-09-07 | 65% |
| API-24 | Realtime auth fallback | David | 2025-09-05 | 30% |
```

### Links

```markdown
Here is a [sample link](https://example.com).
```

### Inline Code

```markdown
Here is some inline code: `var x = 10;`
```

## Examples

### Math

Use `includeMath` to enable LaTeX rendering.

```tsx
<Markdown includeMath>{markdownWithLatex}</Markdown>
```

**Display integral:**
```latex
$$\int_0^\infty e^{-x} \, dx = 1$$
```

**Basel problem:**
```latex
$$\sum_{n=1}^\infty \frac{1}{n^2} = \frac{\pi^2}{6}$$
```

**Matrix (bmatrix):**
```latex
$$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}$$
```

**Piecewise (cases):**
```latex
$$f(x) = \begin{cases} x^2 & x \geq 0 \\ -x & x < 0 \end{cases}$$
```
