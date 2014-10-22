
# Typography

## Overview
The Calcite Type System uses a combination of mixins and helper classes to achieve a clear visual style, focusing primarily on simplifying typesetting processes. Using the mixins and classes properly will ensure that all properties are consistent, beutiful, and robust.

## Typefaces
We expose four sets of type families for use in Calcite Web; a Header Family, a Body Family, a Secondary Family, and a Code Family. Each of these type families have a set of weights and styles, defined by their application. For example, the Header Family has more weights than the Body family, reflecting its role as primary UI face, and heavy lifting header face.

The typographic pallete for Calcite Web differs slightly from the official Esri branding document. All typefaces are examined in detail below.

### Header - Avenir Next
[Avenir Next](http://www.fonts.com/font/linotype/avenir-next) is a recut of the classic Avenir typeface, by Adrian Frutiger and Akira Kobayashi. It has been reworked for use on the web, and contains more weights, styles, and other improvements. Avenir Next improves on Avenir in specifically web settings.

Applies the the header face, along with a set of smart weight interactions and typographic defaults, to an element.

```scss
@include header-face();
<!-- or -->
@extend .header-face;
```

```html
<span class="header-face">Avenir Next</span>
```

### Body - Frutiger
While there is no official Esri brand typeface for long for applications, Calcite Web employs [Frutiger](http://www.fonts.com/font/linotype/frutiger?QueryFontType=Web) for this purpose. Frutiger evokes some of the stronger qualities of our default typefaces - Lucida Grande and Segoe UI - while presenting a consistent voice across platforms. Frutiger pairs remarkably well with Avenir, as they are both designed by Adrian Frutiger, with strong influences from Univers.

```scss
@include body-face();
<!-- or -->
@extend .body-face;
```

```html
<span class="body-face">Frutiger</span>
```

### Secondary - ITC Charter
[ITC Charter](http://www.fonts.com/font/itc/itc-charter), designer by Mathew Carter, is used as a Serif alternative to the sans-serif body face. While usage should be sparse, Charter provides the opportunity to add variation and contrast to a pages pallete.

```scss
@include secondary-face();
<!-- or -->
@extend .secondary-face;
```

```html
<span class="secondary-face">ITC Charter</span>
```

### Code - Consolas
Designed by Microsoft's Lucas DeGroot, [Consolas](http://www.fonts.com/font/microsoft-corporation/consolas) is a clean, readable, and simple monospace face for documenting code blocks.

```scss
@include code-face();
<!-- or -->
@extend .code-face;
```

```html
<span class="code-face">Consolas</span>
```

## Weights
Calcite Web provides a set of weights for each typeface. These are used by either using the helper class in html, or the writing sass to include the mixin, or extending the helper class. The available weights for each face are below.

```html
<!-- Avenir Next -->
<span class="header-light">Avenir Next Light</span>
<span class="header-face">Avenir Next Regular</span>
<span class="header-demi">Avenir Next Demi</span>
<span class="header-bold">Avenir Next Bold</span>
<!-- Frutiger -->
<span class="body-face">Frutiger Regular</span>
<span class="body-bold">Frutiger Bold</span>
<!-- ITC Charter -->
<span class="secondary-face">ITC Charter Regular</span>
<span class="secondary-bold">ITC Charter Bold</span>
<!-- Consolas -->
<span class="code-face">Consolas</span>
```

## Styles
Proper care has been taken to ensure that all type systems used by Calcite avoid faux-bold and faux-italics styled by the browser.

## Type Composition Helpers
Adding the following classes lets you apply type styles while composing a page in html.

## SASS Type Composition Mixins
Calcite web provides a suite of SASS mixins to assist with composing type. These mixins don't compile any css by themselves, but added in to CSS that you write will make the process of creating new designs easier.

### Text Inline
Sets the display style of the element to inline

### Text Center
Centers the text.

### Text Left
Left aligns the text.

### Text Right
Right aligns the text,

### Text Rule
Adds a one pixel border bottom to the element.

### Text Large
Sets the font size of the element to one step of the typgraphic scale from the body size.

### Text Small
Sets the font size font of the elements to one step down the typographic scale from the body size.

### Text Light
Sets the opacity of the element to a standardized value.

### Text Ellipsis
Adds a set of styles to the element that will cause the any text overflow to be hidden, truncated with an ellipsis. Useful for long keeping long strings on text to a single line.

### List Bulleted
Adds the calcite styles for bulleted lists to an unordered list.

### List Numbered
Adds the calcite styles for large numbered lists to an ordered list. Useful for listing steps in a process.

### Text Color
Sets the text color of the element to the value entered.

### Link Color
Sets the color and hover color of the element to the given values.

## Font Size
The Calcite Web type system uses a modular typographic scale to ensure a consistent tonal range within all text elements. This modular scale is created from the body size of the type, and a second, smaller size. These two type sizes anchor the scale, and using a precise ratio can be expanded to an entire set of sizes for all typographic needs.

The `font-size($n)` mixin takes an integer, positive or negative, and sets all type within the element to the size defined by traversing that number of steps up or down the typographic scale.

The `font-size($n)` mixin relies on the `modular-scale($n)` mixin to define the scale, and apply it to typographic elements.

## Modular Scale
The `modular-scale($n)` behaves the same as the `font-size($n)` mixin, but returns a raw rem value rather than css styles specific to type elements. This means that the `modular-scale($n)` mixin can be used to define heights, widths, padding, margins, or any other property of an element so that it adheres to the modular scale defined by the tyopgraphy.

Setting the max width of an article to a large multiple of the text size is a way to define a comfortable reading measure related to the proportional decisions of the content.

## Unicode Variables
SASS Unicode variables provide a simple way to display unicode characters as content in css declarations.


## Leading
Leading is the space between lines in a text block. The `leading($n)` mixin accepts an integer, and sets the line height of the element to the integer times the standard baseline unit.

## Tracking
Tracking is the space between letters in a work. The `tracking($n)` mixin accepts an integer, and applies letterspacing to the element as fractions of 1/1000 of an em.
`@include tracking(500)` will apply 1/2 em letterspacing.
`@include tracking(166)` will apply a hairline em letterspacing.

## Word Spacing
Word spacing is - well - the space between words.  The `word-spacing($n)` mixin accepts an integer, and applies letterspacing to the element as fractions of 1/1000 of an em.
`@include word-spacing(500)` will apply 1/2 em word spacing.
`@include word-spacing(166)` will apply a hairline em word spacing.






















