# AnimateLayoutGroup

> Animate width & height of lists of components as they enter and exit

## Usage

```tsx
import { AnimateLayoutGroup } from "@openai/apps-sdk-ui/components/Transition"
```

## Overview

`<AnimateLayoutGroup>` is an abstraction around `<TransitionGroup>` specifically designed for rendering lists of components, while batteries-included transition animations that can also animate height and width of transitions.

All of the same properties from `<Animate>` are supported here, as well as new properties for customizing the timing of layout transitions - `layoutEnter`, `layoutExit`, and `layoutMove`.

### When to use

`<AnimateLayoutGroup>` is great for animating lists of components that should naturally affect layout of surrounding DOM nodes.

## Examples

### Vertical list

(Click to remove)

```tsx
<>
  <Line className="py-2" />
  <AnimateLayoutGroup
    initial={{ y: -10, opacity: 0, blur: 0 }}
    enter={{ y: 0, delay: 150, duration: 600 }}
    exit={{ scale: 0.8, blur: 10, duration: 500 }}
    layoutEnter={{ duration: 400, timingFunction: "ease" }}
    layoutExit={{ delay: 150 }}
  >
    {list.map(({ id }) => (
      <div key={id} className="py-2">
        <PrimaryLine onClick={() => handleRemove(id)} />
      </div>
    ))}
  </AnimateLayoutGroup>
  <Line className="py-2" />
</>
```

### Horizontal list

(Click to remove)

```tsx
<>
  <Square className="px-2" />
  <AnimateLayoutGroup dimension="width">
    {list.map(({ id }) => (
      <div key={id} className="px-2">
        <PrimarySquare onClick={() => handleRemove(id)} />
      </div>
    ))}
  </AnimateLayoutGroup>
  <Square className="px-2" />
</>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| className | Class passed to wrapping elements. `string` | - |
| children* | Components controlled by TransitionGroup rendering. `ReactNode` | - |
| as | Determines the tag used by wrapping elements. `"div"` \| `"span"` | - |
| insertMethod | Determines how new children are added to the children array. `"append"` \| `"prepend"` | - |
| preventInitialTransition | Determines if children should have an enter transition applied during mounting of the TransitionGroup. `boolean` | `true` |
| hideOverflow | Determines if overflow: hidden is applied to the wrapper element. `boolean` | `false` |
| itemAnchor | Determines which side of the container the items will pin to during enter/exit. `"start"` \| `"end"` | `"start"` |
| dimension | Determines which property will be animated during transitions. `"width"` \| `"height"` | `"height"` |
| layoutEnter | Layout enter transition definition. `LayoutTransitionDefinition` | - |
| layoutExit | Layout exit transition definition. `LayoutTransitionDefinition` | - |
| layoutMove | Layout move transition definition. `LayoutTransitionDefinition` | - |
| enter | Styles applied to the enter transition. `TransitionDefinition` | - |
| exit | Styles applied to the exit transition. `TransitionDefinition` | - |
| initial | Styles applied before the enter transition occurs. `InitialTransitionDefinition` | - |
| transitionClassName | Class applied to the inner TransitionGroup. `string` | - |
| forceCompositeLayer | Applies will-change to force animating elements to composite layers. Use with caution! `boolean` | `false` |
