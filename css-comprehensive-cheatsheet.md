# CSS Comprehensive Cheatsheet

## Basic Syntax

```css
selector {
  property: value;
}
```

## Selectors

### Universal Selector
```css
* {
  property: value;
}
```

### Type Selector
```css
element {
  property: value;
}
```

### Class Selector
```css
.classname {
  property: value;
}
```

### ID Selector
```css
#idname {
  property: value;
}
```

### Attribute Selector
```css
[element="value"] {
  property: value;
}
```

### Pseudo-class Selectors
```css
element:hover {
  property: value;
}

element:focus {
  property: value;
}

element:first-child {
  property: value;
}

element:last-child {
  property: value;
}
```

### Pseudo-element Selectors
```css
element::before {
  property: value;
}

element::after {
  property: value;
}
```

### Combinators
```css
/* Descendant combinator */
ancestor descendant {
  property: value;
}

/* Child combinator */
parent > child {
  property: value;
}

/* Adjacent sibling combinator */
previous + next {
  property: value;
}

/* General sibling combinator */
previous ~ siblings {
  property: value;
}
```

## Box Model

```css
element {
  width: value;
  height: value;
  padding: value;
  margin: value;
  border: value;
  box-sizing: border-box; /* or content-box */
}
```

## Display

```css
element {
  display: none;
  display: block;
  display: inline;
  display: inline-block;
  display: flex;
  display: grid;
}
```

## Flexbox

```css
container {
  display: flex;
  flex-direction: row | row-reverse | column | column-reverse;
  justify-content: flex-start | flex-end | center | space-between | space-around;
  align-items: flex-start | flex-end | center | baseline | stretch;
}

item {
  flex: value;
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

## Grid

```css
container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  grid-template-rows: value;
  gap: value;
}

item {
  grid-column: value;
  grid-row: value;
}
```

## Positioning

```css
element {
  position: static | relative | absolute | fixed | sticky;
  top: value;
  right: value;
  bottom: value;
  left: value;
  z-index: value;
}
```

## Colors

```css
element {
  color: value;
  background-color: value;
  opacity: value;
}
```

## Typography

```css
element {
  font-family: value;
  font-size: value;
  font-weight: normal | bold | bolder | lighter | 100 - 900;
  font-style: normal | italic | oblique;
  line-height: value;
  text-align: left | right | center | justify;
  text-decoration: none | underline | overline | line-through;
  text-transform: none | capitalize | uppercase | lowercase;
  letter-spacing: value;
  word-spacing: value;
}
```

## Background

```css
element {
  background-color: value;
  background-image: url(path/to/image);
  background-repeat: repeat | repeat-x | repeat-y | no-repeat;
  background-position: left top | x% y% | xpos ypos;
  background-size: auto | length | cover | contain;
  background-attachment: scroll | fixed | local;
}
```

## Border

```css
element {
  border: border-width border-style border-color;
  border-width: value;
  border-style: none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset;
  border-color: value;
  border-radius: value;
}
```

## Margin and Padding

```css
element {
  margin: value; /* top right bottom left */
  padding: value; /* top right bottom left */
}
```

## Transitions

```css
element {
  transition-property: property;
  transition-duration: time;
  transition-timing-function: linear | ease | ease-in | ease-out | ease-in-out;
  transition-delay: time;
}
```

## Transforms

```css
element {
  transform: translate(x, y);
  transform: rotate(angle);
  transform: scale(x, y);
  transform: skew(x-angle, y-angle);
}
```

## Animations

```css
element {
  animation-name: name;
  animation-duration: time;
  animation-timing-function: linear | ease | ease-in | ease-out | ease-in-out;
  animation-delay: time;
  animation-iteration-count: number | infinite;
  animation-direction: normal | reverse | alternate | alternate-reverse;
  animation-fill-mode: none | forwards | backwards | both;
}

@keyframes name {
  from {
    property: value;
  }
  to {
    property: value;
  }
}
```

## Media Queries

```css
@media screen and (max-width: size) {
  element {
    property: value;
  }
}
```

## Useful Units

- `px` - Pixels
- `%` - Percentage
- `em` - Relative to the font-size of the element
- `rem` - Relative to the font-size of the root element
- `vw` - Relative to 1% of the viewport's width
- `vh` - Relative to 1% of the viewport's height

## Common Properties

```css
element {
  cursor: pointer | default | text | move | not-allowed | help;
  overflow: visible | hidden | scroll | auto;
  visibility: visible | hidden | collapse;
  z-index: number;
}
```