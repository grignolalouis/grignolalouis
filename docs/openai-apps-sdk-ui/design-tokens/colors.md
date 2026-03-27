# Colors

> Color palettes and semantic color tokens

## Primitive Colors

### Gray Scale

Gray values are inverted between light and dark themes for consistent contrast.

#### Light Theme

| Token | Value | Description |
|-------|-------|-------------|
| `--gray-0` | `#ffffff` | White |
| `--gray-25` | `#fcfcfc` | Lightest gray |
| `--gray-50` | `#f9f9f9` | |
| `--gray-75` | `#f3f3f3` | |
| `--gray-100` | `#ededed` | |
| `--gray-150` | `#dfdfdf` | |
| `--gray-200` | `#cdcdcd` | |
| `--gray-250` | `#b9b9b9` | |
| `--gray-300` | `#afafaf` | |
| `--gray-350` | `#9f9f9f` | |
| `--gray-400` | `#8f8f8f` | |
| `--gray-450` | `#767676` | |
| `--gray-500` | `#5d5d5d` | Mid gray (shared) |
| `--gray-550` | `#4f4f4f` | |
| `--gray-600` | `#414141` | |
| `--gray-650` | `#393939` | |
| `--gray-700` | `#303030` | |
| `--gray-750` | `#282828` | |
| `--gray-800` | `#212121` | |
| `--gray-850` | `#1c1c1c` | |
| `--gray-900` | `#181818` | |
| `--gray-925` | `#161616` | |
| `--gray-950` | `#131313` | |
| `--gray-975` | `#101010` | |
| `--gray-1000` | `#0d0d0d` | Darkest gray |

### Alpha Transparency

Alpha values use `color-mix()` with the `--alpha-base` color (black in light, white in dark).

| Token | Opacity |
|-------|---------|
| `--alpha-0` | 0% |
| `--alpha-02` | 2% |
| `--alpha-04` | 4% |
| `--alpha-05` | 5% |
| `--alpha-06` | 6% |
| `--alpha-08` | 8% |
| `--alpha-10` | 10% |
| `--alpha-12` | 12% |
| `--alpha-15` | 15% |
| `--alpha-16` | 16% |
| `--alpha-20` | 20% |
| `--alpha-25` | 25% |
| `--alpha-30` | 30% |
| `--alpha-35` | 35% |
| `--alpha-40` | 40% |
| `--alpha-50` | 50% |
| `--alpha-60` | 60% |
| `--alpha-70` | 70% |

### Green

| Token | Value |
|-------|-------|
| `--green-25` | `#edfaf2` |
| `--green-50` | `#d9f4e4` |
| `--green-75` | `#b8ebcc` |
| `--green-100` | `#8cdfad` |
| `--green-200` | `#66d492` |
| `--green-300` | `#40c977` |
| `--green-400` | `#04b84c` |
| `--green-500` | `#00a240` |
| `--green-600` | `#008635` |
| `--green-700` | `#00692a` |
| `--green-800` | `#004f1f` |
| `--green-900` | `#003716` |
| `--green-950` | `#011c0b` |
| `--green-1000` | `#001207` |

Alpha variants: `--green-a25`, `--green-a50`, `--green-a75`, `--green-a100`, `--green-a200`, `--green-a300`

### Red

| Token | Value |
|-------|-------|
| `--red-25` | `#fff0f0` |
| `--red-50` | `#ffd9d9` |
| `--red-75` | `#ffc6c5` |
| `--red-100` | `#ffa4a2` |
| `--red-200` | `#ff8583` |
| `--red-300` | `#ff6764` |
| `--red-400` | `#fa423e` |
| `--red-500` | `#e02e2a` |
| `--red-600` | `#ba2623` |
| `--red-700` | `#911e1b` |
| `--red-800` | `#6e1615` |
| `--red-900` | `#4d100e` |
| `--red-950` | `#280b0a` |
| `--red-1000` | `#1f0909` |

Alpha variants: `--red-a25`, `--red-a50`, `--red-a75`, `--red-a100`, `--red-a200`, `--red-a300`

### Blue

| Token | Value |
|-------|-------|
| `--blue-25` | `#f5faff` |
| `--blue-50` | `#e5f3ff` |
| `--blue-75` | `#cce6ff` |
| `--blue-100` | `#99ceff` |
| `--blue-200` | `#66b5ff` |
| `--blue-300` | `#339cff` |
| `--blue-400` | `#0285ff` |
| `--blue-500` | `#0169cc` |
| `--blue-600` | `#004f99` |
| `--blue-700` | `#003f7a` |
| `--blue-800` | `#013566` |
| `--blue-900` | `#00284d` |
| `--blue-950` | `#000e1a` |
| `--blue-1000` | `#000d19` |

Alpha variants: `--blue-a25`, `--blue-a50`, `--blue-a75`, `--blue-a100`, `--blue-a200`, `--blue-a300`

### Yellow

| Token | Value |
|-------|-------|
| `--yellow-25` | `#fffbed` |
| `--yellow-50` | `#fff6d9` |
| `--yellow-75` | `#ffeeb8` |
| `--yellow-100` | `#ffe48c` |
| `--yellow-200` | `#ffdb66` |
| `--yellow-300` | `#ffd240` |
| `--yellow-400` | `#ffc300` |
| `--yellow-500` | `#e0ac00` |
| `--yellow-600` | `#ba8e00` |
| `--yellow-700` | `#916f00` |
| `--yellow-800` | `#6e5400` |
| `--yellow-900` | `#4d3b00` |
| `--yellow-950` | `#261d00` |
| `--yellow-1000` | `#1a1400` |

Alpha variants: `--yellow-a25`, `--yellow-a50`, `--yellow-a75`, `--yellow-a100`, `--yellow-a200`, `--yellow-a300`

### Orange

| Token | Value |
|-------|-------|
| `--orange-25` | `#fff5f0` |
| `--orange-50` | `#ffe7d9` |
| `--orange-75` | `#ffcfb4` |
| `--orange-100` | `#ffb790` |
| `--orange-200` | `#ff9e6c` |
| `--orange-300` | `#ff8549` |
| `--orange-400` | `#fb6a22` |
| `--orange-500` | `#e25507` |
| `--orange-600` | `#b9480d` |
| `--orange-700` | `#923b0f` |
| `--orange-800` | `#6d2e0f` |
| `--orange-900` | `#4a2206` |
| `--orange-950` | `#281105` |
| `--orange-1000` | `#211107` |

Alpha variants: `--orange-a25`, `--orange-a50`, `--orange-a75`, `--orange-a100`, `--orange-a200`, `--orange-a300`

### Purple

| Token | Value |
|-------|-------|
| `--purple-25` | `#f9f5fe` |
| `--purple-50` | `#efe5fe` |
| `--purple-75` | `#e0cefd` |
| `--purple-100` | `#ceb0fb` |
| `--purple-200` | `#be95fa` |
| `--purple-300` | `#ad7bf9` |
| `--purple-400` | `#924ff7` |
| `--purple-500` | `#8046d9` |
| `--purple-600` | `#6b3ab4` |
| `--purple-700` | `#532d8d` |
| `--purple-800` | `#3f226a` |
| `--purple-900` | `#2c184a` |
| `--purple-950` | `#160c25` |
| `--purple-1000` | `#100a19` |

Alpha variants: `--purple-a25`, `--purple-a50`, `--purple-a75`, `--purple-a100`, `--purple-a200`, `--purple-a300`

### Pink

| Token | Value |
|-------|-------|
| `--pink-25` | `#fff4f9` |
| `--pink-50` | `#ffe8f3` |
| `--pink-75` | `#ffd4e8` |
| `--pink-100` | `#ffbada` |
| `--pink-200` | `#ffa3ce` |
| `--pink-300` | `#ff8cc1` |
| `--pink-400` | `#ff66ad` |
| `--pink-500` | `#e04c91` |
| `--pink-600` | `#ba437a` |
| `--pink-700` | `#963c67` |
| `--pink-800` | `#6e2c4a` |
| `--pink-900` | `#4d1f34` |
| `--pink-950` | `#29101c` |
| `--pink-1000` | `#1a0a11` |

Alpha variants: `--pink-a25`, `--pink-a50`, `--pink-a75`, `--pink-a100`, `--pink-a200`, `--pink-a300`

### Constant Colors

| Token | Value |
|-------|-------|
| `--white` | `#ffffff` |
| `--black` | `#000000` |

---

## Semantic Colors

### Text Colors

| Token | Light | Dark | Description |
|-------|-------|------|-------------|
| `--color-text` | `--gray-1000` | `--gray-1000` | Primary text |
| `--color-text-inverse` | `--gray-0` | `--gray-0` | Inverse text |
| `--color-text-secondary` | `--gray-500` | `--gray-700` | Secondary text |
| `--color-text-tertiary` | `--gray-400` | `--gray-600` | Tertiary text |
| `--color-text-disabled` | `--gray-400` | `--gray-500` | Disabled text |

### Semantic Color Categories

Each semantic color has tokens for various states and variants:

#### Info (Blue)

| Token | Description |
|-------|-------------|
| `--color-text-info` | Info text color |
| `--color-background-info-soft` | Soft background |
| `--color-background-info-solid` | Solid background |
| `--color-border-info-outline` | Outline border |

#### Success (Green)

| Token | Description |
|-------|-------------|
| `--color-text-success` | Success text color |
| `--color-background-success-soft` | Soft background |
| `--color-background-success-solid` | Solid background |
| `--color-border-success-outline` | Outline border |

#### Warning (Orange)

| Token | Description |
|-------|-------------|
| `--color-text-warning` | Warning text color |
| `--color-background-warning-soft` | Soft background |
| `--color-background-warning-solid` | Solid background |
| `--color-border-warning-outline` | Outline border |

#### Caution (Yellow)

| Token | Description |
|-------|-------------|
| `--color-text-caution` | Caution text color |
| `--color-background-caution-soft` | Soft background |
| `--color-background-caution-solid` | Solid background |
| `--color-border-caution-outline` | Outline border |

#### Danger (Red)

| Token | Description |
|-------|-------------|
| `--color-text-danger` | Danger text color |
| `--color-background-danger-soft` | Soft background |
| `--color-background-danger-solid` | Solid background |
| `--color-border-danger-outline` | Outline border |

#### Discovery (Purple)

| Token | Description |
|-------|-------------|
| `--color-text-discovery` | Discovery text color |
| `--color-background-discovery-soft` | Soft background |
| `--color-background-discovery-solid` | Solid background |
| `--color-border-discovery-outline` | Outline border |

### Border Colors

| Token | Light | Dark | Description |
|-------|-------|------|-------------|
| `--color-border-subtle` | `--alpha-05` | `--alpha-06` | Subtle borders |
| `--color-border` | `--alpha-10` | `--alpha-12` | Default borders |
| `--color-border-strong` | `--alpha-15` | `--alpha-20` | Strong borders |

### Surface Colors

| Token | Light | Dark | Description |
|-------|-------|------|-------------|
| `--color-surface` | `--gray-0` | `--gray-200` | Primary surface |
| `--color-surface-secondary` | `--gray-50` | `--gray-100` | Secondary surface |
| `--color-surface-tertiary` | `--gray-75` | `--gray-50` | Tertiary surface |
| `--color-surface-elevated` | `--gray-0` | `--gray-300` | Elevated surface |
| `--color-surface-elevated-secondary` | `--gray-50` | `--gray-400` | Secondary elevated |

### Ring Color

| Token | Light | Dark |
|-------|-------|------|
| `--color-ring` | `--blue-500` | `--blue-400` |
