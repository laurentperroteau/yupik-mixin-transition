Yupik Transition
================

## reworking in progress !

### Useful placeholders for CSS3 transition

>  Equivalent to jQuery slide up/down and fade in/out, work in IE9+ (working in IE8 but without transition), using compass.

Install using Bower:

    $ bower install --save yupik-transition


How does this work?
-------------------

Import compass:
````scss
@import "compass/css3/opacity";
@import "compass/css3/transition";
````

Change settings if you need:
````scss
$yupik-transition-duration  : 200ms;
$yupik-transition-ease      : linear;
````

Copy these transition placeholders  in your style:
````scss
%transition-slide-up { 
    max-height: 0; 
    overflow: hidden; visibility: hidden;
    @include transition-slide-animation;
    // or
    // @include transition-slide-animation(myDuration myEasing);
}

%transition-slide-down { 
    max-height: 500px; // change value if block higher than 500px
    visibility: visible;
}

%transition-opacity-zero { 
    @include opacity(0); visibility: hidden;
    @include transition-opacity-transition;
}

%transition-opacity-one { 
    @include opacity(1); visibility: visible;
}
````

And in your style:
````scss
.block {
    @extend %transition-slide-up;

    &.is-open {
        @extend %transition-slide-down;
    }
}
````