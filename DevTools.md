# DEV DOCUMENTATION

## BEM

* Block
* Element `__`
* Modifier(s) `--`

BEM is a highly useful, powerful, and simple naming convention that makes your front-end code easier to read and understand, easier to work with, easier to scale, more robust and explicit, and a lot more strict.

HTML :

```html
<ul class="headerNav headerNav--xmas">
  <li class="headerNav__item">
    <a href="" class="headerNav__itemLink">About</a>
  </li>
  <li class="headerNav__item">
    <a href="" class="headerNav__itemLink headerNav__itemLink--active">Home</a>
  </li>
  <li class="headerNav__item">
    <a href="" class="headerNav__itemLink headerNav__itemLink--isDisabled">My Account</a>
  </li>
</ul>
```
SCSS example :

``` css
.headerNav{
  display:flex;
  justify-content:space-between;
  &--xmas{
    background:red;
  }
  &__item{
    list-style:none;
  }
  &__itemLink{
    color:white;
    text-decoration:none;
    &--isDisabled{
      color:grey;
    }
    &--isActive{
      color:green;
    }
  }
}
```

## PSEUDO ATTRIBUTE ::after & ::before

::before creates a pseudo-element that is the first child of the selected element & ::after creates a pseudo-element that is the last child of the selected element.
They're often used to add cosmetic content to an element with the content property. They're inline by default.

HTML :

```html
<section class="cover">
  <h2 class="cover__title">Présentation</h2>
</section>
```
SCSS example :

```css
.cover {
  &__title{
    font-size: 24px;
    color: #bbb;
    text-align: center;
    &::before,
    &::after{
      content: '';
      position: absolute;
      top: 0;
      display: block;
      width: 50px;
      height: 50px;
      background: green;
    }
    &::before{
      left:0;
    }
    &::after{
      right:0;
    }
  }
}
```

## UNITS

### REM (Root EM)

The em unit is relative to the font-size of the parent, which causes the compounding issue. The rem unit is relative to the root—or the html—element. That means that we can define a single font size on the html element and define all rem units to be a percentage of that.

CSS example :

```css
html { font-size: 62.5%; }
body { font-size: 1.4rem; } /* =14px */
h1   { font-size: 2.4rem; } /* =24px */
```

### EM

The EM unit is relative to the current element's font-size or viewport size :
1em is the same as the font-size of the current element.
The default base font-size given to web pages by web browsers before CSS styling is applied is 16 pixels, which means the computed value of 1em is 16 pixels for an element by default.

SCSS example :

```CSS
.cover {
  font-size : 100%; /* 100% = 16px */
  &__mainTitle {
    /* 1em = 16px */
    font-size: .8em;
  }
}
```

### VW / VH

They're relative units, which are relative to the current element's font-size or viewport size:
Respectively these are 1/100th of the width of the viewport, and 1/100th of the height of the viewport.

## FLEXBOXGRID

FlexBoxGrid is a grid system based on the flex display property.

* Responsive <br/>
Responsive modifiers enable specifying different column sizes, offsets, alignment and distribution at xs, sm, md & lg viewport widths.

```html
<div class="row">
    <div class="col-xs-12
                col-sm-8
                col-md-6
                col-lg-4">
        <div class="box">Responsive</div>
    </div>
</div>
```

* Fluid <br/>
Percent based widths allow fluid resizing of columns and rows.

```css
.col-xs-6 {
  flex-basis: 50%;
}
```

* Simple Syntax <br/>
All you need to remember is row, column, content.

```html
<div class="row">
    <div class="col-xs-12">
        <div class="box">12</div>
    </div>
</div>
```
[FlexBoxGrid Documentation](http://flexboxgrid.com/)

## USEFUL LINKS

### Front-end Job Interview Questions

* [See the Questions](https://github.com/h5bp/Front-end-Developer-Interview-Questions)

### CSS NEXT (future of css)

* [Visit the site](http://cssnext.io/features/)
