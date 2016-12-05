Sass col utility
============

This is a small sass utility for easily creating sized cols in a flexbox grid. It uses Zurb's foundation breakpoint function, with a set of size classes.

####settings/variables/_breakpoints.scss
Contains a sass map with breakpoint values:

```scss
$breakpoints: (
   small: 0,
   medium: 640px,
   large: 1000px, // iPad landscape
   xlarge: 1025px, // Above iPad landscape
   xxlarge: 1440px,
);
```

####tools/mixins/_breakpoint.scss

Contains the actual breakpoint mixin. A couple of usage examples:

```scss
.c-some-class {
  @include breakpoint(medium) { // medium and up
  }
  @include breakpoint(large only) { // large only
  }
  @include breakpoint(400px) { // custom breakpoint 400px and up
  }
  @include breakpoint(portrait) { // portrait screens
  }
  @include breakpoint(retina) { // retina screens
  }
}
```

###trumps/utils/_u-col-size.scss

Enable the used classes by settings these variables to true or false
```scss
$include-1-2-up: true;
$include-1-2-only: true;
$include-1-3-up: true;
$include-1-3-only: true;
$include-2-3-up: true;
$include-2-3-only: true;
$include-1-4-up: true;
$include-1-4-only: true;
$include-3-4-up: true;
$include-3-4-only: true;
$include-1-5-up: true;
$include-1-5-only: true;
$include-2-5-up: true;
$include-2-5-only: true;
$include-3-5-up: true;
$include-3-5-only: true;
$include-4-5-up: true;
$include-4-5-only: true;
$include-1-6-up: true;
$include-1-6-only: true;
```

Change the margin between cols by adjusting the margin map:
```scss
$margin: (
  small: .25rem,
  medium: .5rem,
  large: .5rem,
  xlarge: .5rem
);
```

Use it like so:
```html
<div class="u-1/4@m">
  This will be 1/4 wide on medium and up
</div>
```

Or mix it up!
```html
<div class="u-1/2@s u-1/4@m">
  This will be 1/2 wide on mobile and 1/4 wide on medium and up
</div>
```

Add `-o` for only breakpoints:
```html
<div class="u-1/3@s-o u-1/5@m-o u-1/6@l">
  This will be 1/3 wide on small only, 1/5 on medium only and 1/6 on large up
</div>
```
