# Advanced Landing Page Mockup

# Cool New CSS Features

## Header

    Background clip

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
