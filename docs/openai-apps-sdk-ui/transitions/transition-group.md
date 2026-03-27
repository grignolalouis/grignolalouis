# TransitionGroup

> Primitive for rendering components over time

## Usage

```tsx
import { TransitionGroup } from "@openai/apps-sdk-ui/components/Transition"
```

## Overview

`<TransitionGroup>` manages the mounting and unmounting of components over time by controlling the rendering of children passed to the component.

When children are mounted and unmounted, `<TransitionGroup>` wraps the components with a containing element and applies stateful data attributes for entering and exiting transitions.

The timing of component rendering and stateful data attributes is based on `enterDuration` and `exitDuration` values. Children must provide a stable key to correctly keep track of component references.

### When to use

Always reach for `<Animate>`, `<AnimateLayout>`, or `<AnimateLayoutGroup>` before using `<TransitionGroup>` directly.

Direct use of this primitive should only be necessary for very complex transitions with many moving parts.

```tsx
// JSX
<TransitionGroup className={s.Example} enterDuration={2000} exitDuration={1000}>
  {show && <Square key="s" />}
</TransitionGroup>

// CSS
.Example {
  &[data-entering] {
    opacity: 0;
  }

  &[data-exiting] {
    opacity: 1;
  }

  &[data-entering-active],
  &[data-exiting][data-interrupted] {
    opacity: 1;
    box-shadow: 0 0 0 5px green;
    transition: opacity 2s ease, box-shadow 2s ease;
  }

  &[data-exiting-active],
  &[data-entering][data-interrupted] {
    opacity: 0;
    box-shadow: 0 0 0 5px red;
    transition: opacity 1s ease, box-shadow 1s ease;
  }
}
```

## Transition states

There are two types of transitions, `enter` and `exit`, and five total data attributes that represent the possible state of transitions.

The transition data attributes are transient, only applied while they are relevant. When a given transition is completed, attributes are removed.

No styles are provided by default from `<TransitionGroup>`.

| Attribute | Description |
|-----------|-------------|
| data-entering | Component enter transition is about to start - useful for staging enter animation styles. Remains applied through the entire entrance transition. |
| data-entering-active | Component enter transition is active. |
| data-exiting | Component exit transition is about to start - useful for staging exit animation styles. Remains applied through the entire exit transition. |
| data-exiting-active | Component exit transition is active. |
| data-interrupted | Component was animating, but then changed to the opposite transition before the original transition completed. For example, an exiting component was re-mounted again, or an entering component was removed before completing entrance. |

## Initial mount transitions

By default, `<TransitionGroup>` prevents initial transitions of children components when it itself is mounted to the DOM.

For specific situations where you want children of the `<TransitionGroup>` to transition as it's mounted, pass `preventInitialTransition={false}`.

In the above example, `<Sample>` will experience an initial enter transition when the TransitionGroup is rendered.

```tsx
<TransitionGroup preventInitialTransition={false}>
  {show && <Sample key="s" />}
</TransitionGroup>
```

## Reference

| Name | Description | Default |
|------|-------------|---------|
| children* | Components controlled by TransitionGroup rendering. `ReactNode` | - |
| as | Determines the tag used by wrapping elements. `"div"` \| `"span"` | - |
| className | Class passed to wrapping elements. `string` | - |
| transitionId | Identifier passed to wrapping elements as `[data-transition-id]`. `string` | - |
| enterDuration | Determines the amount of time that the enter state is applied during mounting. `number` | - |
| exitDuration | Determines the amount of time that the exit state is applied before unmounting. `number` | - |
| preventInitialTransition | Determines if children should have an enter transition applied during mounting of the TransitionGroup. `boolean` | `true` |
| enterMountDelay | Delay in MS to wait before mounting a child. null for no delay (default). `number` | - |
| disableAnimations | Render children changes immediately, bypassing transition timings. `boolean` | - |
| insertMethod | Determines how new children are added to the children array. `"append"` \| `"prepend"` | - |
| style | Styles applied to wrapping elements. `CSSProperties` | - |
| ref | Ref for the TransitionGroup. `Ref<unknown>` | - |
| onEnter | Callback fired when an enter animation is staged (e.g., component mounted to the DOM). `TransitionGroupChildCallback` | - |
| onEnterActive | Callback fired when an enter animation starts. `TransitionGroupChildCallback` | - |
| onEnterComplete | Callback fired when an enter animation completes. `TransitionGroupChildCallback` | - |
| onExit | Callback fired when an exit animation is staged. `TransitionGroupChildCallback` | - |
| onExitActive | Callback fired when an exit animation starts. `TransitionGroupChildCallback` | - |
| onExitComplete | Callback fired when an exit animation completes (e.g., component unmounted from the DOM). `TransitionGroupChildCallback` | - |
