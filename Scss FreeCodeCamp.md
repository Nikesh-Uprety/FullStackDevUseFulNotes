## - Styles can be stored in a varaible staring with $ ($color: red;)
## - Child elements can be nested;
```scss
nav {
  background-color: red;

  ul {
    list-style: none;

    li {
      display: inline-block;
    }
  }
}
```
# Create Reusable CSS with Mixins
```scss
@mixin box-shadow($x, $y, $blur, $c){ 
  -webkit-box-shadow: $x $y $blur $c;
  -moz-box-shadow: $x $y $blur $c;
  -ms-box-shadow: $x $y $blur $c;
  box-shadow: $x $y $blur $c;
}
```
```scss
div {
  @include box-shadow(0px, 0px, 4px, #fff);
}
```
# Use @if and @else to Add Logic To Your Styles
```scss
@mixin text-effect($val) {
  @if $val == danger {
    color: red;
  }
  @else if $val == alert {
    color: yellow;
  }
  @else if $val == success {
    color: green;
  }
  @else {
    color: black;
  }
}

.text {
 @include text-effect(success);
}

```
# Use @for to Create a Sass Loop
```html
<style type='text/scss'>

@for $j from 1 to 6 {
  .text-#{$j} { font-size: 15px * $j; }
}

</style>

<p class="text-1">Hello</p>
<p class="text-2">Hello</p>
<p class="text-3">Hello</p>
<p class="text-4">Hello</p>
<p class="text-5">Hello</p>
```
# Use @each to Map Over Items in a List
```html
<style type='text/scss'>

@each $color in blue, black, red {
  .#{$color}-bg {background-color: $color;}
}


  div {
    height: 200px;
    width: 200px;
  }
</style>

<div class="blue-bg"></div>
<div class="black-bg"></div>
<div class="red-bg"></div>
```
# Apply a Style Until a Condition is Met with @while
```html
<style type='text/scss'>

$x: 1;
@while $x < 6 {
  .text-#{$x} { font-size: 15px * $x;}
  $x: $x + 1;
}

</style>

<p class="text-1">Hello</p>
<p class="text-2">Hello</p>
<p class="text-3">Hello</p>
<p class="text-4">Hello</p>
<p class="text-5">Hello</p>

```
# Extend One Set of CSS Styles to Another Element
```html
<style type='text/scss'>
  h3{
    text-align: center;
  }
  .info{
    width: 200px;
    border: 1px solid black;
    margin: 0 auto;
  }
.info-important {
    @extend .info;
    background-color:magenta;
}



</style>
<h3>Posts</h3>
<div class="info-important">
  <p>This is an important post. It should extend the class ".info" and have its own CSS styles.</p>
</div>

<div class="info">
  <p>This is a simple post. It has basic styling and can be extended for other uses.</p>
</div>
```
