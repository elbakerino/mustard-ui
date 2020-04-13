# Senf-UI, a Mustard-UI Fork

Global concept changes:

- space / spacings for configurable gutters etc.
    - on root container (e.g. panels) only margin-bottom, no top
- often available modifier `.dense|-dense`
- font-sizes use em instead of px
- new import style prio

## Components

### Panels

Selectors:

- `.panel-image`
- `.panel-hero-image`
- `.panel-body-dense`

### Loading

Loading animation

Variables:

```scss
$loading-ring-width: 6px;
$loading-size: 80px;
$loading-size-dense: 40px;
$loading-color: $color-gray-600;
```

Selectors:

- `.loading`
- `.loading.dense`

## Elements

### Buttons

Removed the line-height and added y-paddings, better true-center for any font-family, introduces problems when adding icons (should be solved with `ic-btn`)

Overwriting the default button selectors:

```scss
$button-class: ".btn";
$button-selector: "#{$button-class}, button, input[type='button'], input[type='reset'], input[type='submit']" !default;
```

Selectors: 

- `#{button-class}-raw` for no border and bg

### Lists

Selectors:

- `.no-list`

### Sidebars

- removed hover/focus from `sidebar-category`, new variant: `sidebar-collapsible`

### Typography 

Variables:
```scss
$font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", sans-serif !default;
$font-family-mono: "SF Mono", "Segoe UI Mono", "Roboto Mono", Menlo, Courier, monospace !default;
$text-colors: (
  'primary' : $brand-color,
  'success' : $color-green-500,
  'info' : $color-gray-500,
  'warning' : $color-amber-600,
  'danger' : $color-red-500,
  'light' : $color-gray-50,
  'dark' : $color-gray-900,
  'accent' : $color-blue-700,
) !default;
```

Mixins:
- `title1` to `title6`
- `body1($factor)`, `body2`

Selectors:
- `.body1`, `.body2`
- `.bold`
- `.italic`
- `.mono`
- `.upper`, `.lower`, `.capitalize` for text-transforms
- `.color-primary`, `.color-success`, ... like defined in the var 

## Utilities

### Containers

```scss
$container-gutter: space(4) 0 !default;
```

- `.container.w-fixed`
- `.container-fluid`
- `.container-respoonsive`

### Display

- `.display-flex`
- `.display-inline-flex`
- `.display-inline`
- `.display-grid`

### Elevation

```scss
$elevation-steps: (
  0: none,
  1: 0 2px 4px rgba($color-gray-500, 0.5),
  2: 0 2px 6px rgba($color-gray-600, 0.6),
  3: 0 3px 6px rgba($color-gray-600, 0.7),
  4: 0 4px 6px rgba($color-gray-600, 0.7),
) !default;
```

Mixins:
- `elevation(4)`

Selectors:
- `.ev-0` to `.ev-4`, like defined

### Grid

- changed scope of modifier (`.col-reverse`, `.row-reverse`)
- changed `col-xs-<n>` to `col-<n>`
- `.flex-wrap` 
- `.flex-nowrap` 
- `.flex-column`
- `.row`
- Grid
    - `.display-grid`
    - `.cols-gap-0` to `.cols-gap-4`, like defined in spacings
    - `.cols-one`, `.cols-sm-one` to `.cols-xlg-one`
    - `.cols-two` ...
    - `.cols-three` ...
    - `.cols-four` ...
    - `.cols-five` ...
    - `.cols-six` ...

### Position

Selectors:

- `.absolute`
- `.relative`
- `.fixed`
- `.sticky`
- `.pos-0` for top, right, bottom, left with `0`
- `.top-0`
- `.right-0`
- `.bottom-0`
- `.left-0`

### Spacings

Variables:

```scss
$spacing: 5px !default;
$spacings-def: (0: 0, 1: 1, 2: 2, 3: 3, 4: 4) !default;
$spacings-out-responsive: false !default;
```

Functions:

```scss
/// space(size)
.some {
    margin-left: space(2)
}
```

Spacings in all other elements, utilities etc. are based on `$spacing * map-get($spacings-def, 1)`

Selectors:

- Margins:
    - `.mt-a`, `.mr-a`, `.mb-a`, `.ml-a` auto margins
    - `.m-0`, `.m-1`, `.m-2`, `.m-3` for all around
    - `.my-0`, `.my-1`, `.my-2`, `.my-3` for y-axis gutter
    - `.mx-0`, `.mx-1`, `.mx-2`, `.mx-3` for x-axis gutter
    - `.mt-0`, `.mt-1`, `.mt-2`, `.mt-3` for top
    - `.mr-0`, `.mr-1`, `.mr-2`, `.mr-3` for right
    - `.mb-0`, `.mb-1`, `.mb-2`, `.mb-3` for bottom 
    - `.ml-0`, `.ml-1`, `.ml-2`, `.ml-3` for left
- Paddings:
    - `.p-0`, `.p-1`, `.p-2`, `.p-3` for all around
    - `.py-0`, `.py-1`, `.py-2`, `.py-3` for y-axis gutter
    - `.px-0`, `.px-1`, `.px-2`, `.px-3` for x-axis gutter
    - `.pt-0`, `.pt-1`, `.pt-2`, `.pt-3` for top
    - `.pr-0`, `.pr-1`, `.pr-2`, `.pr-3` for right
    - `.pb-0`, `.pb-1`, `.pb-2`, `.pb-3` for bottom 
    - `.pl-0`, `.pl-1`, `.pl-2`, `.pl-3` for left

### Sections

Variables:

```scss
$section-class: '.section';
$section-selector: '#{$section-class}, section';
```

### Flex-Alignment

Selectors:

- `.items-start`
- `.items-center`
- `.items-end`
