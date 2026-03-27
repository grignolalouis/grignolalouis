# Animate

> Animate components as they mount and unmount

## Usage

```tsx
import { Animate } from "@openai/apps-sdk-ui/components/Transition"
```

## Overview

`<Animate>` is an abstraction around `<TransitionGroup>` for batteries-included transition animations.

`enter`, `exit`, and `initial` props allow you to define the behavior of the animation from a set of GPU-accelerated properties. Animatable properties include `opacity`, `x`, `y`, `scale`, `rotate`, `skewX`, `skewY`, and `blur`.

### When to use

`<Animate>` is great for transitions that don't need to affect the layout of surrounding DOM nodes. Typically, this will mean components with a fixed size or absolute positioning.

These animations should be for transitioning between two states that occupy the same space, such as:

- nothing → Component
- Component → nothing
- Component → AnotherComponent

## Examples

### Fade

By default, `<Animate>` provides a simple fade in/out transition, using ease timing functions.

```tsx
<Animate className="w-[200px] h-[200px]">
  {visible && <Square key="s" />}
</Animate>
```

### Grow

You can extend the basic fade behavior by providing transform properties to `enter`, `exit`, and `initial`.

When transform properties are passed, our cubic timing functions (`--cubic-enter` and `--cubic-exit`) are automatically applied.

```tsx
<Animate
  className="w-[200px] h-[200px]"
  enter={{ scale: 1 }}
  exit={{ scale: 0.5, blur: 20 }}
>
  {visible && <Square key="s" />}
</Animate>
```

### Continuous transitions

By default, `<Animate>` basically "toggles" between enter and exit definitions. You can differentiate entrance and exit transitions by using the `initial` property.

This example is a bit silly, but a practical example would be creating transitions with an emphasized entrance and subtle exit.

```tsx
<Animate
  className="w-[200px] h-[200px]"
  initial={{ x: 120, skewX: 30 }}
  enter={{ duration: 800 }}
  exit={{ x: -120, skewX: -8, duration: 500 }}
>
  {visible && <Square key="s" />}
</Animate>
```

### Cross fade

Easily create cross fade effects between components, like `<CopyButton>`'s icon animation, or larger elements like page transitions.

```tsx
<Button size="2xl" iconSize="xl" variant="soft" onClick={handleClick}>
  <Animate
    className="w-[var(--button-icon-size)] h-[var(--button-icon-size)]"
    enter={{ scale: 1, delay: 150, duration: 400 }}
    exit={{ scale: 0.6, duration: 150 }}
  >
    {copied ? <Check key="copied" /> : <Copy key="copy" />}
  </Animate>
</Button>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| className | Class passed to wrapping elements. `string` | - |
| children* | Components controlled by TransitionGroup rendering. `ReactNode` | - |
| as | Determines the tag used by wrapping elements. `"div"` \| `"span"` | - |
| insertMethod | Determines how new children are added to the children array. `"append"` \| `"prepend"` | - |
| preventInitialTransition | Determines if children should have an enter transition applied during mounting of the TransitionGroup. `boolean` | `true` |
| transitionClassName | Class applied to the inner TransitionGroup. `string` | - |
| enter | Styles applied to the enter transition. `TransitionDefinition` | - |
| exit | Styles applied to the exit transition. `TransitionDefinition` | - |
| initial | Styles applied before the enter transition occurs. `InitialTransitionDefinition` | - |
| transitionPosition | Determines how transition states are positioned. `"static"` \| `"absolute"` | `"absolute"` |
| forceCompositeLayer | Applies will-change to force animating elements to composite layers. Use with caution! `boolean` | `false` |
