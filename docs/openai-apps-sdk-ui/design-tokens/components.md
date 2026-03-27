# Component Tokens

> Component-specific design tokens

## Alert

| Token | Value |
|-------|-------|
| `--alert-border-radius` | `var(--radius-xl)` |
| `--alert-gap` | `calc(var(--spacing) * 3)` (12px) |
| `--alert-gutter` | `calc(var(--spacing) * 4)` (16px) |
| `--alert-font-size` | `var(--font-text-sm-size)` |
| `--alert-line-height` | `var(--font-text-sm-line-height)` |
| `--alert-title-font-weight` | `var(--font-weight-semibold)` |

## Avatar

| Token | Value |
|-------|-------|
| `--avatar-radius` | `var(--radius-full)` |
| `--avatar-size` | `28px` |
| `--avatar-font-size-scaling` | `0.5` |
| `--avatar-overflow-font-size-scaling-one` | `0.45` |
| `--avatar-overflow-font-size-scaling-two` | `0.37` |
| `--avatar-overflow-font-size-scaling-three` | `0.3` |
| `--avatar-image-border-color` | Light: `--alpha-04`, Dark: `--alpha-15` |

## AvatarGroup

| Token | Value |
|-------|-------|
| `--avatar-group-cutout-width` | `3px` |
| `--avatar-group-cutout-color` | `var(--color-surface)` |
| `--avatar-group-spacing` | `-8px` |

## Badge

| Token | SM | MD | LG |
|-------|----|----|-----|
| `--badge-gutter-*` | `5px` | `6px` | `8px` |
| `--badge-size-*` | `20px` | `22px` | `24px` |
| `--badge-radius-*` | `4px` | `4px` | `6px` |
| `--badge-font-size-*` | `12px` | `14px` | `14px` |
| `--badge-font-weight-*` | semibold | semibold | semibold |

## Button

| Token | Value |
|-------|-------|
| `--button-gap-sm` | `3px` |
| `--button-gap-md` | `4px` |
| `--button-gap-lg` | `6px` |
| `--button-font-weight` | `var(--font-weight-medium)` |

## Input

| Token | Value |
|-------|-------|
| `--input-gap-xs` | `4px` |
| `--input-gap-sm` | `6px` |
| `--input-gap-md` | `8px` |
| `--input-gap-lg` | `10px` |
| `--input-text-color` | `var(--color-text)` |
| `--input-placeholder-text-color` | `var(--color-text-tertiary)` |
| `--input-outline-border-color` | `var(--color-border-primary-outline)` |
| `--input-outline-border-color-hover` | Light: `--alpha-25`, Dark: `--alpha-30` |
| `--input-outline-border-color-focus` | `var(--alpha-50)` |
| `--input-soft-background-color` | `var(--color-background-primary-soft-alpha)` |
| `--input-soft-border-color-focus` | `var(--alpha-20)` |
| `--input-border-color-invalid` | Light: `--red-500`, Dark: `--red-600` |

## Link

| Token | Value |
|-------|-------|
| `--link-font-weight` | `inherit` |
| `--link-gap` | `calc(var(--spacing) * 0.5)` (2px) |
| `--link-radius` | `var(--radius-sm)` |
| `--link-underline-decoration-offset` | `0.1em` |
| `--link-primary-text-color` | Light: `--blue-500`, Dark: `--blue-300` |
| `--link-primary-text-color-hover` | Light: `--blue-800`, Dark: `--blue-400` |

## Menu

| Token | Value |
|-------|-------|
| `--menu-gutter` | `calc(var(--spacing) * 1.5)` (6px) |
| `--menu-radius` | `var(--radius-xl)` |
| `--menu-font-size` | `var(--font-text-sm-size)` |
| `--menu-line-height` | `var(--font-text-sm-line-height)` |
| `--menu-item-padding` | `6px 8px` |
| `--menu-item-gap` | `6px` |
| `--menu-item-background-color` | Light: `--alpha-08`, Dark: `--alpha-10` |
| `--menu-separator-background-color` | `var(--color-border)` |
| `--menu-radio-indicator-size` | `var(--font-text-lg-size)` |
| `--menu-checkbox-indicator-size` | `var(--font-text-lg-size)` |

## Popover

| Token | Value |
|-------|-------|
| `--popover-radius` | `var(--radius-xl)` |

## RadioGroup

| Token | Value |
|-------|-------|
| `--radio-group-col-gap` | `calc(var(--spacing) * 2.5)` (10px) |
| `--radio-group-row-gap` | `calc(var(--spacing) * 5)` (20px) |
| `--radio-group-item-gap` | `calc(var(--spacing) * 1.5)` (6px) |
| `--radio-group-item-font-size` | `var(--font-text-sm-size)` |
| `--radio-group-item-line-height` | `var(--font-text-sm-line-height)` |
| `--radio-group-indicator-size` | `var(--font-text-md-size)` |
| `--radio-group-indicator-border-color` | `var(--color-border-primary-outline)` |
| `--radio-group-indicator-border-color-hover` | `var(--alpha-25)` |
| `--radio-group-indicator-background-color` | `var(--color-background-primary-solid)` |
| `--radio-group-indicator-hole-size` | `0.375rem` (6px) |

## SegmentedControl

| Token | Value |
|-------|-------|
| `--segmented-control-gap` | `2px` |
| `--segmented-control-gutter` | `2px` |
| `--segmented-control-font-weight` | `var(--font-weight-semibold)` |
| `--segmented-control-thumb-shadow` | `0 1px 4px -1px rgb(0 0 0 / 20%)` |
| `--segmented-control-background` | Light: `--gray-100`, Dark: `--gray-0` |
| `--segmented-control-thumb-background` | Light: `--gray-0`, Dark: `--gray-300` |

## SelectControl

| Token | Value |
|-------|-------|
| `--select-control-font-weight` | `var(--font-weight-medium)` |

## Slider

| Token | Light | Dark |
|-------|-------|------|
| `--slider-track-color` | `--gray-150` | `--gray-400` |
| `--slider-range-color` | `--gray-450` | `--gray-600` |

## Switch

| Token | Value |
|-------|-------|
| `--switch-track-width` | `32px` |
| `--switch-track-height` | `19px` |
| `--switch-thumb-offset` | `3px` |
| `--switch-thumb-size` | `13px` (calculated) |
| `--switch-thumb-shadow` | `0 1px 2px rgb(0 0 0 / 20%)` |
| `--switch-label-gap` | `calc(var(--spacing) * 2)` (8px) |

### Switch Colors

| Token | Light | Dark |
|-------|-------|------|
| `--switch-track-color` | `--gray-150` | `--gray-400` |
| `--switch-track-color-hover` | `--gray-200` | `--gray-450` |
| `--switch-track-color-checked` | `--gray-900` | `--blue-400` |
| `--switch-track-color-disabled` | `--gray-100` | `--gray-300` |
| `--switch-thumb-color` | `--gray-0` | `--gray-1000` |

## CodeBlock

| Token | Value |
|-------|-------|
| `--codeblock-background-color` | `var(--gray-25)` |

### Syntax Highlighting Colors

| Token | Light | Dark |
|-------|-------|------|
| `--codeblock-syntax-1` | `#c0660d` | `--yellow-100` |
| `--codeblock-syntax-2` | `--blue-500` | `--blue-200` |
| `--codeblock-syntax-3` | `--green-600` | `--green-300` |
| `--codeblock-syntax-4` | `--pink-500` | `--pink-500` |
| `--codeblock-syntax-5` | `--purple-500` | `--purple-300` |

## Dialog

| Token | Value |
|-------|-------|
| `--dialog-min-width` | `250px` |
| `--dialog-max-width` | `450px` |
| `--dialog-container-inner-padding` | `calc(var(--spacing) * 5)` (20px) |
| `--dialog-backdrop-fade-background` | `color-mix(in oklab, var(--color-surface-elevated) 60%, transparent)` |
| `--dialog-backdrop-dim-background` | Light: `rgb(0 0 0 / 30%)`, Dark: `rgb(0 0 0 / 50%)` |

## Modal

| Token | Value |
|-------|-------|
| `--modal-container-inner-padding` | `calc(var(--spacing) * 5)` (20px) |
| `--modal-backdrop-background` | Light: `rgb(0 0 0 / 30%)`, Dark: `rgb(0 0 0 / 50%)` |

## Chat

| Token | Value |
|-------|-------|
| `--chat-max-width` | `800px` |
| `--chat-gutter` | `calc(var(--spacing) * 5)` (20px) |
| `--chat-background-color` | `var(--color-surface)` |
| `--thread-gutter` | `calc(var(--spacing) * 4)` (16px) |
| `--composer-gutter` | `calc(var(--spacing) * 3)` (12px) |
| `--composer-compact-gutter` | `calc(var(--spacing) * 2)` (8px) |
| `--composer-radius` | `var(--radius-4xl)` |
| `--composer-background-color` | `var(--color-surface-elevated)` |
| `--user-message-text-color` | `var(--color-text)` |
| `--user-message-background-color` | Light: `--alpha-05`, Dark: `--alpha-08` |
