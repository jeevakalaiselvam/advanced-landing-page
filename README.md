# Advanced Landing Page Natours

## Common Concepts

### Background clip

    background-image: linear-gradient(
            to right bottom,
            rgba($color-primary-light, 0.8),
            rgba($color-primary-dark, 0.8)
        ),
        url(../images/hero.jpg);
    background-size: cover;
    background-position: top;
    -webkit-clip-path: polygon(0 0, 100% 0, 100% 75%, 0% 100%);
    clip-path: polygon(0 0, 100% 0, 100% 75%, 0% 100%);
    position: relative;

### SASS Variable for Theme Colors

    $color-primary: #55c57a;
    $color-primary-light: #7ed56f;
    $color-primary-dark: #28b485;
    $color-secondary-light: #ffb900;
    $color-secondary-dark: #ff7730;
    $color-tertiary-light: #2998ff;
    $color-tertiary-dark: #5643fa;

### Mixins for commonly used properties

    @mixin clear-fix {
    &::after {
        content: '';
        display: table;
        clear: both;
    }

    @include clear-fix

### Object Fit full width Video

    .bg-video {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        z-index: -1;
        opacity: 0.15;

        &__content {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }

### Multi Composition images

    .composition {
        position: relative;

        &__photo {
            width: 55%;
            box-shadow: 0 1.5rem 40rem rgba($color-black, 0.4);
            border-radius: 2px;
            position: absolute;
            z-index: 10;
            outline-offset: 1rem;
            transition: all 0.2s;

            &--p1 {
                left: 0;
                top: -2rem;
            }
            &--p2 {
                right: 0;
                top: 2rem;
            }

            &--p3 {
                left: 20%;
                top: 10rem;
            }

            &:hover {
                outline: 1rem solid $color-primary;
                transform: scale(1.05);
                cursor: pointer;
                box-shadow: 0 2.5rem 40rem rgba($color-black, 0.5);
                z-index: 20;
            }

            &:hover &__photo:not(:hover) {
                transform: scale(0.9);
            }
        }
    }

### Gradient Image Clip

    &__icon {
        font-size: 6rem;
        display: inline-block;
        background-image: linear-gradient(
            to right,
            $color_primary-light,
            $color-primary-dark
        );
        background-clip: border-box;
        -webkit-background-clip: text;
        color: transparent;
    }

### Gradient Backgrounds and Blend modes

    background-image: linear-gradient(
                    to right bottom,
                    $color-primary-light,
                    $color-primary-dark
                ),url(../images/nat-6.jpg);
    background-blend-mode: screen;

### SASS Mixins for Media Queries

    @mixin respond-phone {
        @media (max-width: 600px) {
            @content;
        }
    }

    @include respond-phone {
        font-size: 50%;
    }

### Mixins using Breakpoints

    /*
    Breakpoint choices
    - phone
    - tab-port
    - tab-lab
    - big-desktop
    */

    @mixin respond($breakpoint) {
        @if $breakpoint == phone {
            @media (max-width: 600px) {
                @content;
            }
        }
    }
