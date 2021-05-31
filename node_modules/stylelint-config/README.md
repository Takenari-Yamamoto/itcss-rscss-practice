# Stylelint Config

[![Greenkeeper badge](https://badges.greenkeeper.io/JohannesFischer/stylelint-config.svg)](https://greenkeeper.io/)

## Colors

### Color Hex Case

Specify hex colors in lowercase.

[Rule](http://stylelint.io/user-guide/rules/color-hex-case/)

```
"color-hex-case": "lower"
```

__Example__

```
// Bad

a {
  color: #FFF;
}

// Good

a {
  color: #000;
}

a {
  color: #fff;
}
```

### Color Hex Length

Specify short notation for hex colors.

[Rule](http://stylelint.io/user-guide/rules/color-hex-length/)

```
"color-hex-length": "short"
```

__Example__

```
// Bad

a {
  color: #ffffff;
}

a {
  color: #fffffaa;
}

// Good

a {
  color: #fff;
}

a {
  color: #fffa;
}

a {
  color: #a4a4a4;
}
```

### Color Named


Colors must never be named.

[Rule](http://stylelint.io/user-guide/rules/color-named/)

```
"color-named": "never"
```

__Example__

```
// Bad

a {
  color: black;
}

// Good

a {
  color: #000;
}

a {
  color: rgb(0, 0, 0);
}

a {
  color: var(--foo-color-white);
}

a {
  color: $blue;
}

a {
  color: @blue;
}
```

### No Invalid Hex

Disallow invalid hex colors.

[Rule](http://stylelint.io/user-guide/rules/color-no-invalid-hex/)

```
"color-no-invalid-hex": true
```

__Example__

```
// Bad

a {
  color: #00;
}

a {
  color: #fff1az;
}

a {
  color: #12345aa;
}

// Good

a {
  color: #000;
}
```

## Functions

Skipped for now: http://stylelint.io/user-guide/rules/#function

## Numbers

### Number Leading Zero

There must never be a leading zero.

[Rule](http://stylelint.io/user-guide/rules/number-leading-zero/)

```
"number-leading-zero": "never"
```

__Example__

```
// Bad

a {
  line-height: 0.5;
}

a {
  transform: translate(2px, 0.4px);
}

// Good

a {
  line-height: .5;
}

a {
  transform: translate(2px, .4px);
}
```

### Numbers No Trailing Zeros

Numbers must have no trailing zeros.

[Rule](http://stylelint.io/user-guide/rules/number-no-trailing-zeros/)

```
"number-no-trailing-zeros": true
```

__Example__

```
// Bad

a {
  top: 1.0px;
}

a {
  top: 1.01000px;
}

// Good

a {
  top: 1px;
}

a {
  top: 1.01px;
}
```

## Strings

### String Quotes

Strings must always be wrapped with double quotes.

[Rule](http://stylelint.io/user-guide/rules/string-quotes/)

```
"string-quotes": "double"
```

__Example__

```
// Bad

a {
  content: 'x';
}

a[id='foo'] {
  display: none;
}

// Good

a {
  content: "x";
}

a[id="foo"] {
  display: none;
}
```

## Length

### Length Zero No Unit

Disallow units for zero lengths.

[Rule](http://stylelint.io/user-guide/rules/length-zero-no-unit/)

```
"length-zero-no-unit": true
```

__Example__

```
// Bad

a {
  top: 0px;
}

a {
  top: 0.000em;
}

// Good

a {
  top: 0;
}
```

## Units

### Unit Case

Specify units in lowercase.

[Rule](http://stylelint.io/user-guide/rules/unit-case/)

```
"unit-case": "lower"
```

__Example__

```
// Bad

a {
  width: 10PX;
}

a {
  width: 10Px;
}

a {
  width: 10PIXEL;
}

// Good

a {
  width: 10px;
}

a {
  width: calc(10px * 2);
}
```

## Values

### Value Keyword Case

Specify keyword values in lowercase.

[Rule](http://stylelint.io/user-guide/rules/value-keyword-case/)

```
"value-keyword-case": "lower"
```

__Example__

```
// Bad

a {
  display: Block;
}

a {
  display: BLOCK;
}

// Good

a {
  display: block;
}
```

### Value No Vendor Prefix

Avoid vendor prefixes for values and use autoprefixer instead.

[Rule](http://stylelint.io/user-guide/rules/value-no-vendor-prefix/)

```
"value-no-vendor-prefix": true
```

__Example__

```
// Bad

.foo {
  display: -webkit-flex;
}

.foo {
  max-width: -moz-max-content;
}

.foo {
  background: -webkit-linear-gradient(bottom, #000, #fff);
}

// Good

.foo {
  display: flex;
}

.foo {
  max-width: max-content;
}

.foo { background: linear-gradient(bottom, #000, #fff); }
```

## Value Lists

Value lists must always have a single space after the commas and be written in a single line.

[Rule](http://stylelint.io/user-guide/rules/value-list-comma-newline-after/)
[Rule](http://stylelint.io/user-guide/rules/value-list-comma-newline-before/)
[Rule](http://stylelint.io/user-guide/rules/value-list-comma-space-after/)
[Rule](http://stylelint.io/user-guide/rules/value-list-comma-space-before/)

```
"value-list-comma-newline-after": "never-multi-line",
"value-list-comma-newline-before": "never-multi-line",
"value-list-comma-space-after": "always",
"value-list-comma-space-before": "never"
```

__Example__

```
// Bad

a {
  background-size: 100px,150px;
}

a {
  background-size: 100px ,150px;
}

// Nope

a {
  background-size: 100px,
                   150px;
 }

a {
  background-size: 100px
                   , 150px;
}

// Good

a {
  background-size: 100px, 150px;
}
```

## Shorthand Property

Shorthand properties must not have redundant values.

[Rule](http://stylelint.io/user-guide/rules/shorthand-property-no-redundant-values/)

```
"shorthand-property-no-redundant-values": true
```

__Example__

```
// Bad

.foo {
  margin: 1px 1px;
}

.foo {
  margin: 1px 1px 1px 1px;
}

.foo {
  padding: 1px 2px 1px;
}

.foo {
  border-radius: 1px 2px 1px 2px;
}

// Good

.foo {
  margin: 1px;
}

.foo {
  margin: 1px 1px 1px 2px;
}

.foo {
  padding: 1px 1em 1pt 1pc;
}

.foo {
  border-radius: 10px / 5px;
}
```

## Properties

### Case

Properties must be specified in lowercase.

[Rule](http://stylelint.io/user-guide/rules/property-case/)

```
"property-case": "lower"
```

__Example__

```
// Bad

a {
  Width: 1px
}

a {
  WIDTH: 1px
}

// Good

a {
  width: 1px
}

a {
  animation-duration: 3s;
}
```

### No Vendor Prefix

Properties must be specified without vendor prefixes, use autoprefixer instead

[Rule](http://stylelint.io/user-guide/rules/property-no-vendor-prefix/)

```
"property-no-vendor-prefix": true
```

__Example__

```
// Bad

a {
  -webkit-animation-duration: 3s;
}

// Good

a {
  animation-duration: 3s;
}
```

## Declaration

### Bangs

Important declarations should be avoid if possible but if used the bang of declarations must have white space before but not after.

[Rule](http://stylelint.io/user-guide/rules/declaration-bang-space-after/)

```
"declaration-bang-space-after": "never",
"declaration-bang-space-before": "always"
```

__Example__


```
// Bad

a {
  color: #fff ! important;
}

a {
  color: #000!important;
}

// Good

a {
  color: #f00 !important;
}
```

### Colon

There must always be a single space after the colon but not before.

[Rule](http://stylelint.io/user-guide/rules/declaration-colon-space-after/)
[Rule](http://stylelint.io/user-guide/rules/declaration-colon-space-before/)

```
"declaration-colon-space-after": "always",
"declaration-colon-space-before": "never"
```

__Example__

```
// Bad

a {
  color :#f00;
}

a {
  color:#000;
}

a {
  color : #fff;
}

// Good

a {
  color: #000;
}
```

### Property Value Blacklist

Blacklist of disallowed property and value pairs within declarations.

* __Border:__ Disallow the use of the word none for borders, use 0 instead
* __Transition:__ Disallow the use of all within transitions.

[Rule](http://stylelint.io/user-guide/rules/declaration-property-value-blacklist/)

```
"declaration-property-value-blacklist": {
  "border": ["none"],
  "transition": [/all/]
}
```

__Example__

```
// Bad

a {
  border: none;
  transition: all 1s linear;
}

// Good

a {
  border: 0;
  transition: height 1s linear;
}
```

## Declaration Blocks

### No Duplicated Properties

Consecutive duplicated properties can be used , they can prove to be useful fallbacks for older browsers.


[Rule](http://stylelint.io/user-guide/rules/declaration-block-no-duplicate-properties/)

```
"declaration-block-no-duplicate-properties": [true, {
  "ignore" : ["consecutive-duplicates"]
}]
```

__Example__

```
// Bad

p {
  font-size: 16px;
  font-weight: 400;
  font-size: 1rem;
}

// Good

p {
  font-size: 16px;
  font-size: 1rem;
  font-weight: 400;
}
```

### No Ignored Properties

Avoid property values that are ignored due to another property value in the same rule.

[Rule](http://stylelint.io/user-guide/rules/declaration-block-no-ignored-properties/)

```
"declaration-block-no-ignored-properties": true
```

__Example__

```
// Bad

a {
  display: inline;
  width: 100px;
}

a {
  display: inline;
  height: 100px;
}

a {
  display: inline;
  margin: 10px;
}

a {
  display: block;
  vertical-align: baseline;
}

a {
  display: flex;
  vertical-align: baseline;
}

a {
  position: absolute;
  vertical-align: baseline;
}

a {
  float: left;
  vertical-align: baseline;
}

// Good

a {
  display: inline;
  margin-left: 10px;
}

a {
  display: inline;
  margin-right: 10px;
}

a {
  display: inline;
  padding: 10px;
}

a {
  display: inline-block;
  width: 100px;
}

a {
  display: table-cell;
  vertical-align: baseline;
}

a {
  position: relative;
  vertical-align: baseline;
}
```

### No Shorthand Property Overrides

Avoid shorthand properties that override related longhand properties.

[Rule](http://stylelint.io/user-guide/rules/declaration-block-no-shorthand-property-overrides/)

```
"declaration-block-no-shorthand-property-overrides": true
```

__Example__

```
// Bad

a {
  padding-left: 10px;
  padding: 20px;
}

a {
  transition-property: opacity;
  transition: opacity 1s linear;
}

a {
  border-top-width: 1px;
  top: 0;
  bottom: 3px;
  border: 2px solid blue;
}

// Good

a {
  padding: 10px;
  padding-left: 20px;
}

a {
  transition-property: opacity;
}

a {
  transition: opacity 1s linear;
}
```

### Properties Order

Prefixed properties must always be alphabetically ordered.

[Rule](http://stylelint.io/user-guide/rules/declaration-block-properties-order/)

```
"declaration-block-properties-order": "alphabetical"
```

__Example__

```
// Bad

a {
  top: 0;
  color: pink;
}

a {
  -moz-transform: scale(1);
  transform: scale(1);
  -webkit-transform: scale(1);
}

// Good

a {
  color: pink;
  top: 0;
}

a {
  /* stylelint-disable property-no-vendor-prefix */  
  -moz-transform: scale(1);
  -webkit-transform: scale(1);
  transform: scale(1);
  /* stylelint-enable property-no-vendor-prefix */
}
```

### Semicolon New Line After

Require a newline and disallow whitespace after but never before the semicolons of declaration blocks.


[Rule](http://stylelint.io/user-guide/rules/declaration-block-semicolon-newline-after/)
[Rule](http://stylelint.io/user-guide/rules/declaration-block-semicolon-newline-before/)

```
"declaration-block-semicolon-newline-after": "always",
"declaration-block-semicolon-newline-before": "never-multi-line"
```

__Example__

```
// Bad

a { color: pink; top: 0; }

a {
  color: pink
  ; top: 0;
}

// Good

a {
  color: #000;
  top: 0;
}

a {
  color: #f00; /* end-of-line comment */
  top: 0;
}
```

### Trailing Semicolon

There must always be a trailing semicolon.

[Rule](http://stylelint.io/user-guide/rules/declaration-block-trailing-semicolon/)

```
"declaration-block-trailing-semicolon": "always"
```

__Example__

```
// Bad

a {
  color: #fff
}

a {
  background: #fff;
  color: #000
}

a {
  @include foo
}

// Good

a {
  background: #fff;
  color: #000;
  @include foo;
}
```

## Blocks

### Closing Brace Newline After

Require a newline before and after the closing brace of blocks.

[Rule](http://stylelint.io/user-guide/rules/block-closing-brace-newline-after/)
[Rule](http://stylelint.io/user-guide/rules/block-closing-brace-newline-before/)

```
"block-closing-brace-newline-after": ["always", {
  "ignoreAtRules": ["if", "else"]
}],
"block-closing-brace-newline-before": "always"
```

__Example__

```
// Bad

a { color: pink; } b { color: red; }

a { color: pink;
} b { color: red; }

// Good

a { color: pink; }
b { color: red; }
```

### No Empty

Disallow empty blocks.

[Rule](http://stylelint.io/user-guide/rules/block-no-empty/)

```
"block-no-empty": true
```

__Example__

```
// Bad

a {}

a { }

@media print { a {} }

// Good

a {
  color: #abc;
}

@media print {
  a {
    color: #fff;
  }
}
```

### No Single Line

Disallow single-line blocks.

[Rule](http://stylelint.io/user-guide/rules/block-no-single-line/)

```
"block-no-single-line": true
```

__Example__

```
// Bad

a,
b { color: pink; }

a { color: pink; top: 1px; }

@media print {
  a { color: pink; }
}

a {
  color: red;
  @media print { color: pink; }
}

// Good

a {
  color: pink;
}

a,
b {
  color: pink;
}

@media print {
 a {
   color: pink;
 }
}

a {
  color: red;

  @media print {
    color: pink;
  }
}
```

### Opening Brace Space Before

Require a single space before the opening brace of blocks.

[Rule](http://stylelint.io/user-guide/rules/block-opening-brace-space-before/)

```
"block-opening-brace-space-before": "always"
```

__Example__

```
// Bad

a{
  color: #f0f;
}

// Good
a {

  color: #f0f;
}
```

## Selectors

### Combinator Space

Require a single before and after the combinators of selectors.

[Rule](http://stylelint.io/user-guide/rules/selector-combinator-space-after/)
[Rule](http://stylelint.io/user-guide/rules/selector-combinator-space-before/)

```
"selector-combinator-space-after": "always",
"selector-combinator-space-before": "always"
```

__Example__

```
// Bad

a +b {
  color: #fff;
}

a>b {
  color: #000;
}

// Good

a + b {
  color: #fff;
}

a ~ b {
  color: #fff;
}
```

### Max Specificity

Limit the specificity of selectors.

Visit the Specificity Calculator for visual representation of selector specificity.

This rule ignores selectors with variable interpolation (#{$var}, @{var}, $(var)).

This rule ignores selectors containing the :not() or :matches() pseudo-classes.

This rule resolves nested selectors before calculating the specificity of a selector.

[Rule](http://stylelint.io/user-guide/rules/selector-max-specificity/)

```
"selector-max-specificity": "0,4,0"
```
__Example__

```
// Bad

#id {
  color: #000;
}

.foo .baz .bar .boo {
  color: #fff;
}

.foo .baz {
  & .bar span {
    display: block;
  }
}

.foo {
  color: #f00;

  &.baz .bar p {
    color: #0f0;
  }
}

// Good

div {
  color: #fff;
}

.foo div {
  color: #f00;
}

.foo div {
  & .bar div a {
    color: #fff;
  }
}

.foo {
  & .baz {
    color: #fff;
  }
}

.foo {
  color: #fff;

  & .baz div {
    color: #fff;
  }
}
```

### No ID

Disallow id selectors.

[Rule](http://stylelint.io/user-guide/rules/selector-no-id/)

```
"selector-no-id": true
```

__Example__

```
// Bad

#foo {
  color: #f00;
}
```

### No Universal

Disallow the universal selector.

[Rule](http://stylelint.io/user-guide/rules/selector-no-universal/)

```
"selector-no-universal": true
```

__Example__

```
// Bad

* {
  color: #000;
}

.foo * {
  color: #000;
}
```

### No Vendor Prefix

Disallow vendor prefixes for selectors, prefer using autoprefixer.

[Rule](http://stylelint.io/user-guide/rules/selector-no-vendor-prefix/)

```
"selector-no-vendor-prefix": true
```

__Example__

```
// Bad

input::-moz-placeholder {
  color: eee;
}

:-webkit-full-screen a {
  color: ff0;
}

// Good

input::placeholder {
  color: #eee;
}

:full-screen a {
  color: #ff0;
}
```

### Pseudo Class Case

Pseudo-class selectors must be written in lowercase.

[Rule](http://stylelint.io/user-guide/rules/selector-pseudo-class-case/)

```
"selector-pseudo-class-case": "lower"
```

__Example__

```
// Bad

a:Hover
b:hOvEr,
em:HOVER {
  color: #f00;
}

// Good

a:hover {
  color: #f00;
}
```

## Selector Lists

### Comma Newline

Require a newline after the commas of selector lists but never before.

[Rule](http://stylelint.io/user-guide/rules/selector-list-comma-newline-after/)
[Rule](http://stylelint.io/user-guide/rules/selector-list-comma-newline-before/)

```
"selector-list-comma-newline-after": "always",
"selector-list-comma-newline-before": "never-multi-line"
```

__Example__

```
// Bad

a,b {
  color: #fff;
}

a
, b {
  color: #fff;
}

// Good

a,
b {
  color: #fff;
}
```

## Rules

### Nested Empty Line Before

There must always be an empty line before rules. First nested selectors and selectors after comments will be ignored.

[Rule](http://stylelint.io/user-guide/rules/rule-nested-empty-line-before/)

```
"rule-nested-empty-line-before": ["always", {
  "except": ["first-nested"],
  "ignore" : ["after-comment"]
}]
```

__Example__

```
// Bad

div {

  a {
    color: #fff;
  }
  b {
    color: #000;
  }
}

// Good

div {
  a {
    color: #fff;
  }

  b {
    color: #000;
  }
  // No Comment
  em {
    color: #aaa;
  }
}
```

### Non Nested Empty Line Before

Require or disallow an empty line before non-nested rules.

If the rule is the very first node in a stylesheet then it is ignored.

[Rule](http://stylelint.io/user-guide/rules/rule-non-nested-empty-line-before/)

```
"rule-non-nested-empty-line-before": "always"
```

__Example__

```
// Bad

a {
  color: #fff;
}
b {
  color: #000;
}

// Good

a {
  color: #fff;
}

b {
  color: #000;
}
```

## Media Feature

### Colon Space

Require a single space after but never before the colon in media features.

[Rule](http://stylelint.io/user-guide/rules/media-feature-colon-space-after/)
[Rule](http://stylelint.io/user-guide/rules/media-feature-colon-space-before/)

```
"media-feature-colon-space-after": "always",
"media-feature-colon-space-before": "never"
```

__Example__

```
// Bad

@media (min-width:600px) {
  a {
    color: #fff;
  }
}

@media (max-width : 600px) {
  a {
    color: #000;
  }
}

// Good

@media (min-width: 600px) {
  a {
    color: #fff;
  }
}
```

### No Missing Punctuation

Disallow missing punctuation for non-boolean media features.

[Rule](http://stylelint.io/user-guide/rules/media-feature-no-missing-punctuation/)

```
"media-feature-no-missing-punctuation": true
```

__Example__
```
// Bad

@media (max-width 600px) {
  a {
    color: #fff;
  }
}

@media (width   20em) {
  a {
    color: #fff;
  }
}

// Good

@media (max-width: 600px) {
  a {
    color: #fff;
  }
}

@media (width >= 20em) {
  a {
    color: #fff;
  }
}
```

### Range Operator Space

Require a single space before and after the range operator in media features.

[Rule](http://stylelint.io/user-guide/rules/media-feature-range-operator-space-after/)
[Rule](http://stylelint.io/user-guide/rules/media-feature-range-operator-space-before/)

```
"media-feature-range-operator-space-after": "always",
"media-feature-range-operator-space-before": "always"
```

__Example__

```
// Bad

@media (max-width>=600px) {
  a {
    color: #fff;
  }
}

@media (max-width >=600px) {
  a {
    color: #fff;
  }
}

// Good

@media (max-width >= 600px) {
  a {
    color: #fff;
  }
}
```

## At-rule

### Empty Line Before

Require an empty line before at-rules.

If the at-rule is the very first node in a stylesheet then it is ignored.

[Rule](http://stylelint.io/user-guide/rules/at-rule-empty-line-before/)

```
"at-rule-empty-line-before": ["always", {
  "except": ["first-nested"],
  "ignore" : ["after-comment", "blockless-group"],
  "ignoreAtRules": ["else"]
}],
```

__Example__

```
// Bad

a {
  color: #fff;
  @media (max-width >= 600px) {
    color: #000;
  }
}

// Good

a {
  color: #fff;

  @media (max-width >= 600px) {
    color: #000;
  }
  // No Comment
  @media (max-width >= 1200px) {
    color: #f0f;
  }
}
```

### Name Case

At-rules names must be in lowercase.

[Rule](http://stylelint.io/user-guide/rules/at-rule-name-case/)

```
"at-rule-name-case": "lower"
```

__Example__

```
// Bad

@Charset 'UTF-8';

@MEDIA (min-width: 50em) {
  a {
    color: #fff;
  }
}

// Good

@charset 'UTF-8';

@media (min-width: 50em) {
  a {
    color: #fff;
  }
}
```

### Name Space After

Require a single space after at-rule names.

[Rule](http://stylelint.io/user-guide/rules/at-rule-name-space-after/)

```
"at-rule-name-space-after": "always"
```

__Example__

```
// Bad

@charset"UTF-8";

@media(min-width: 700px) {
  a {
    color: #fff;
  }
}

@media  (min-width: 700px) {
  a {
    color: #fff;
  }
}

@media
(min-width: 700px) {
  a {
    color: #fff;
  }
}

// Good

@charset "UTF-8";

@import url("x.css");

@media (min-width: 700px) {
  a {
    color: #fff;
  }
}
```

## Comments

### Whitespace Inside

Require whitespace on the inside of comment markers.

Any number of asterisks are allowed at the beginning or end of the comment. So `/** comment **/` is treated the same way as `/* comment */`.

[Rule](http://stylelint.io/user-guide/rules/comment-whitespace-inside/)

```
"comment-whitespace-inside": "always"
```

__Example__

```
// Bad

/*comment*/

/*comment */

/** comment**/

// Good

/* comment */

/** comment **/

/**
 * comment
 */

/*     comment
*/
```

## General

### Indentation

Always indent at-rules, rules, comments, declarations, inside parentheses and multi-line values by 2 spaces.

[Rule](http://stylelint.io/user-guide/rules/indentation/)

```
"indentation": 2
```

__Example__

```
// Bad

@media print {
a {
top: 10px;
}
}

@media print {
a {
  top: 10px;
  }
}

@media print {
    a {
      top: 10px;
    }
}

// Good

@media print {
  a {
    top: 10px;
  }
}
```

### Max Empty Lines

Limit the number of adjacent empty lines to one.

[Rule](http://stylelint.io/user-guide/rules/max-empty-lines/)

```
"max-empty-lines": 1
```

__Example__

```
// Bad

a {
  color: #fff;
}


b {
  color: #000;
}

/*
  Comment strings are also checked


  So the following is a warning
*/

// Good

a {
  color: #fff;
}

b {
  color: #000;
}

/**
 * Comment
 *
 * This is not a warning
 */

 /*
  Another Comment

  Also not a warning
*/
 ```

### Max Nesting Depth

Limit the allowed nesting depth to 3.

[Rule](http://stylelint.io/user-guide/rules/max-nesting-depth/)

```
"max-nesting-depth": 3
```

This rule works by checking rules' and at-rules' actual "nesting depth" against your specified max. Here's how nesting depths works:

```
a {
  & b { /* nesting depth 1 */
    & .foo { /* nesting depth 2 */
      @media print { /* nesting depth 3 */
        & .baz { /* nesting depth 4 */
          color: #f00;
        }
      }
    }
  }
}
```

Note that root-level at-rules will not be included in the nesting depth calculation, because most users would take for granted that root-level at-rules are "free" (because necessary). So both of the following .foo rules have a nesting depth of 2, and will therefore pass if your max is less than or equal to 2:

```
a {
  b { /* 1 */
    .foo {} /* 2 */
  }
}
```

### No Duplicate Selectors

Disallow duplicate selectors within a stylesheet.

[Rule](http://stylelint.io/user-guide/rules/no-duplicate-selectors/)

```
"no-duplicate-selectors": true
```

__Example__

```
// Bad

.foo,
.bar,
.foo {
  color: #fff;
}

.foo {}
.bar {}
.foo {}

.foo,
.bar {
  color: #fff;
}

.bar,
.foo {
  color: #fff;
}

// Good

.foo {
  color: #000;
}

@media (min-width: 10px) {
  .foo {
    color: #fff;
  }
}

.foo {
  .foo {
    color: #fff;
  }
}

a b {
  color: #fff;
}

a {
  & b,
  & c {
    color: #000;
  }
}
```

### No EOL Whitespace

Disallow end-of-line whitespace.

[Rule](http://stylelint.io/user-guide/rules/no-eol-whitespace/)

```
"no-eol-whitespace": true
```

__Example__

```
a {
  color: #f00;
}·

a {
  color: #f00;
}····

/* Comment strings are also checked····
 * so the following is a warning */
```

### No Extra Semicolons

Disallow extra semicolons.

[Rule](http://stylelint.io/user-guide/rules/no-extra-semicolons/)

```
"no-extra-semicolons": true
```

__Example__

```
// Bad

@import "x.css";
;

.foo {
  color: #fff;;
}
```

### No Missing End Of Source Newline

Disallow missing end-of-source newlines.

[Rule](http://stylelint.io/user-guide/rules/no-missing-end-of-source-newline/)

```
"no-missing-end-of-source-newline": true
```

__Example__

```
//Good

a { color: pink; }
\n
```
