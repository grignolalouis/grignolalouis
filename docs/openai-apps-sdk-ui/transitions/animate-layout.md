# AnimateLayout

> Animate width & height of components as they mount and unmount

## Usage

```tsx
import { AnimateLayout } from "@openai/apps-sdk-ui/components/Transition"
```

## Overview

`<AnimateLayout>` is an abstraction around `<TransitionGroup>` for batteries-included transition animations that can also animate height and width of transitions.

All of the same properties from `<Animate>` are supported here, as well as new properties for customizing the timing of layout transitions - `layoutEnter`, `layoutExit`, and `layoutMove`.

### When to use

`<AnimateLayout>` is great for transitions should naturally affect layout of surrounding DOM nodes.

These animations should be for transitioning between two states that occupy the same space, such as:

- nothing → Component
- Component → nothing
- Component → AnotherComponent

## Examples

### Height

By default, `<AnimateLayout>` animates the height of a component as it enters and exits the DOM.

```tsx
<>
  <Line className="w-full h-12" />
  <AnimateLayout transitionClassName="pt-4">
    {show && <PrimaryLine key="s" className="w-full h-[80px]" />}
  </AnimateLayout>
  <Line className="w-full h-12 mt-4" />
</>
```

### Width

You can also animate the width of components by passing `dimension="width"`.

```tsx
<div className="flex">
  <Square className="w-[200px] h-[200px]" />
  <AnimateLayout
    dimension="width"
    transitionClassName="pl-6"
    enter={{ delay: 200 }}
    layoutExit={{ delay: 75 }}
  >
    {show && <PrimarySquare key="s" className="w-[200px] h-[200px]" />}
  </AnimateLayout>
  <Square className="w-[200px] h-[200px] ml-6" />
</div>
```

### Accordion

Accordion items are a great example of dynamically introducing content that affect the height of surrounding DOM nodes.

The following example shows how to wrap accordion item content with `<AnimateLayout>` to create a smooth animation.

```tsx
<AnimateLayout
  enter={{ y: 0, delay: 150, duration: 450 }}
  exit={{ y: -8 }}
  layoutEnter={{ duration: 400 }}
>
  {open && (
    <div key="content" className="pb-4 text-secondary">
      {children}
    </div>
  )}
</AnimateLayout>
```

### Talk button

When animating width, the height of the component should be consistent.

The key to making this animation work is using `transitionClassName` to recreate the flexbox structure that `<Button>` normally provides, and stretching it to the full height of the button.

```tsx
<Button
  color={recording ? "danger" : "primary"}
  size="xl"
  iconSize="lg"
  onClick={handleClick}
  loading={sending}
>
  <AnimateLayout dimension="width" transitionClassName="h-full flex items-center gap-2">
    {recording ? (
      <ArrowUp key="recording" />
    ) : (
      <Fragment key="record">
        <Wave /> Talk
      </Fragment>
    )}
  </AnimateLayout>
</Button>
```

## Gotchas

- `<AnimateLayout>` provides a wrapping element, which `className` and layout transition properties are applied to.
- Avoid box model properties on `className`, like `margin`, `padding`, `border`.
  - These are additive to `height: 0;` empty state, and cannot be properly animated.
- Avoid `box-shadow` on `className`, as it will be visible during empty state.
- `margin` cannot be animated, and should be avoided on the children (`transitionClassName`). Use `padding` instead, which is intrinsic to the height calculation!

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
