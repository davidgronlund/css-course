# Three pillars of good html and css

## Responsive design

- Fluid layouts
- Media queries
- Responsive images
- Correct units
- Desktop first vs mobile first

## Maintable and scalable code

- Clean
- Easy to understand
- Growth
- Reusable
- How to organize files
- How to name classes
- How to structure HTML

## Web performance

- Less HTTP requests
- Less code
- Compress code
- Use a preprocessor
- Less images
- Compress images

# What happens to CSS when we load up a webpage

1. Load html
2. Parse html -> Load css -> parse css
3. Browser generate DOM
4. The final css is stored in the css object model (cssom)

DOM and CSSOM forms a `Render tree`

To render the page: visual formatting model

Final rendered website

# Parse CSS

## CSS terminology

- Selectors and declaration blocks

## Cascade

Combine and resolve conflicts between rules and declarations

Importance -> Specificity -> Source order

## Specificity

inline style, id, classes, element (a, div etc.)
(0,0,0,0)

## How css values are processed

Percentage and relative value are always converted to pixels

### Rem font-size

Always relative to root font-size

## How units are converted from relative to absolute (PX)

The percentage based unit is always based on the parent element

### em (font)

3 x parent element computed font-size = (3 \* 24) = 72px

### em (lengths)

x _ current element computed font-size (3 _ 16) = 48px

### rem (font, length)

x \* root computed font-size

#### Why use rem and em's if they are based on font size?

We can build more robust responsive layouts, because by changing font size, we will automatically change length. Gives flexibility.

### vh

1 vh = 1 % of view height

### vw

1 vw = 1 % of view width

# Inheritance

Every css property must have a value -> Is there a cascaded value? If no -> Is the property inherited (yes) -> the computed value is passed (ie. 16 px not 150%)

Props related to text are inherited

Margin etc is not inherited

The computed, not the declared value is inherted

# how and why we use rem uniuts

We want an easy way to set settings to simplify media queries

# The box model

Each element can be seen as a box

## Padding

Inside the box

## Border

Goes around the content and the padding

## Margin

Is whitespace outside the box. Space between boxes.

## Fill area

Area filled by background color/image. content + padding

By default, padding and margin makes up the total width, height of a box. With box-sizing: border-box, they are not included in the total

## Block-level boxes

display:block
100% of parent width
vertically one after another

## Inline boxes

display:inline
content distributed in lines
occupies only content's space
no heights and widths
padding and margins only horizontal

## inline-block

display: inline-block
are inline boxes but work as block level boxes internally
no line breaks
only content's space

# Positioning schemes

##Normal flow

- not floated
- laid out according to source order
  ##Floats
- elemnt is removed from the normal flow
- text and inline elemnt wraps arout floated
- the container willnot ajdust its height to the element (clear-fix solution)
  ##Absolute
- element is removed from normal flow
- no inpact on surrounding elements
- top, right to

# Stacking contexts

# The think, build, architecture mindset

## Think

about layout before building

### Component driven design

- modular building block make up interfaces
- -held together by the layout of the page
- re-usable acress a project or between project
- independent allowing us to use them anywhere on the page

### atomic design

atoms, molecules, organismns, templates, pages

## Build

### Meaningful names

### BEM

block element modifier

- block is a standalone component that is meaningful on its own
- element part of a block that has no standalone meaning
- modifier a different version of a block or an element

## Architect

### The 7-1 pattern

- 7 different folders for partial sass files and 1 main sass file to import all other files into a compiled css stylesheet

### the 7 folders

- base
- components
- layout
- pages
- themes
- abstracts
- vendors
