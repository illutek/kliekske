# 't Kliekske

The idea was to set up my own grid (see below), but afterwards everything was converted to **FLEX**.

## CUSTOM GRID 
``` scss
.col-1-of-2 {
  width: calc((100% - #{$gutter-horizontal}) / 2);
}

.col-1-of-3 {
  width: calc((100% - 2 * #{$gutter-horizontal}) / 3);
}

.col-2-of-3 {
  width: calc(2 * ((100% - 2 * #{$gutter-horizontal}) / 3) + #{$gutter-horizontal});
}

.col-1-of-4 {
  width: calc((100% - 3 * #{$gutter-horizontal}) / 4);
}

.col-2-of-4 {
  width: calc(2 * ((100% - 3 * #{$gutter-horizontal}) / 4) + #{$gutter-horizontal}) ;
}

.col-3-of-4 {
  width: calc(3 * ((100% - 3 * #{$gutter-horizontal}) / 4) + (2 * #{$gutter-horizontal}));
}
```


## FLEX
So no heavy css frame-work like Bootstrap for me.  
https://www.w3schools.com/css/css3_flexbox.asp 

### Webtechnologies
- **Yarn** FAST, RELIABLE, AND SECURE DEPENDENCY MANAGEMENT, for devDependencies primarily for gulp.
- **Bower** for the theme Dependencies
- **Sass** is the most mature, stable, and powerful professional grade CSS extension language in the world.
- **BEM** — Block Element Modifier is a highly useful, powerful, and simple naming convention that makes your 
front-end code easier to read and understand, easier to work with, easier to scale, more robust and explicit, and a lot more strict.
For Drupal i've raised that a level up by converting almost all views to twig files.
- **Gulp** is a toolkit for automating painful or time-consuming tasks in your development workflow.




TODO table override default inline styles ckeditor

## Navigation
Was left: 0; heb dit moeten aanpassen naar right: -100%; omdat de &__list left nog aanklikbaar was.

``` scss
&__nav {
    right: -100%;
}

&__checkbox:checked ~ &__nav {
     opacity: 1;
     width: 100%;
     right: 0;
   }
   
```

## Font Awesome 5

Not all icons come are free disadvantage is if you want to set up your own classes.
 as follows.   
 ``` scss
 .icon {
   font: {
     family: "Font Awesome 5 Free";
     style: normal;
     variant: normal;
   }
   display: inline-block;
   padding-right: .5rem;
   text-rendering: auto;
   -webkit-font-smoothing: antialiased;
 
   &--external-link {
     &::before {
       @extend .icon;
       content: "\f35d";
       font-weight: 900;
     }
   }
 }
 ```
The font-weight set to 900 this because the icon is pro.

## COLORBOX 
Drupal8 module is not responsief out of the box, the solution, an extra js file was added. (js/colorbox.js).
Set up a library.

``` yml
colorboxjs:
  js:
    js/colorbox.js: {}
```
And add this only to the photos-page templates/content/photos/node--photos--full,html.twig  
```twig
{{ attach_library('kliekske/colorboxjs') }}
```

## 