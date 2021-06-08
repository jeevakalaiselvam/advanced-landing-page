# Advanced Landing Page Mockup

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

    @incluse clear-fix

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
