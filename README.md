# Project: Build a Portfolio
## Objective
This project is part of the [Full Stack Web Developer Nanodegree](https://de.udacity.com/course/full-stack-web-developer-nanodegree--nd004/) with the goal of recreating
a design mockup.

## <a href="viewport"></a>Viewport
The viewport defines the area the browser can render content to. Browser report the
width in the number of DIPs (Device Independent Pixels) that is a unit of measurement
that relates pixels to a real distance. Any DIP will take up the same amount of space
on a display regardless of the pixel density of the display. If no viewport is set the
browser renders the page for a screen with `980` pixels. In that regard, the
DPR (Device Pixel Ratio) is the ratio between physical and logical pixels.
If a mobile screen has a resolution of `1920x1080` px with a DPR of 2 the maximum
width of a viewport in CSS pixel is `960`.

```html
<meta name=“viewport” content="width=device-width", init-scale=“1”>`
```

```css
/* max-width on elements prevents overflowing */
img, embed, object, video {
    max-width: 100%;
}
```

```css
/* buttons should be at least 48 pixels wide and 48 pixels tall */
nav a, button {
    min-width:  48px;
    min-height: 48px;
}
```

## Media Queries
Different styles needs to be applied on different devices. Media Queries allow
to selectively apply css.

```html
<link rel=“stylesheet” href=“styles.css”>
<!-- stylesheet over500.css is only applied when the screen is over 500 pixels -->
<link rel=“stylesheet” media=“screen and (min-width:500px)” href=“over500.css”>
```

Media Queries can also be embedded:

```css
@media screen and (min-width:500px) {
    body { background-color: blue; }
}
```

Weigh the costs between linked css and @media:
* linked css: many small files but many http requests
* @media: fewer requests with bigger files

Media queries that are most commonly used are `min-width` and `max-width`.
The point at which the page changes layout is called a breakpoint.

## <a name="flexbox"></a>Flexbox
Illustration of the most common responsive flexbox layouts that reside inside
the [`./flexbox`](./flexbox) folder and described in the following:
* [`./flexbox/flexbox.html`](./flexbox/flexbox.html) implements the flexbox layout illustrating the order property for rearranging the order of the sections.
Breakpoint that changes the order of the layout has been implemented at `700px`. Demo can be found [here](http://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/flexbox/flexbox.html)

* [`./flexbox/columndrop.html`](./flexbox/columndrop.html) implements the responsive
column drop flexbox pattern. Initially, the layout starts with three sections that are aligned one after another. Breakpoints at `450px` and `550px` ensure that the sections will not shrink when resizing and instead the section will be moved on top of one another.
Demo can be found [here](http://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/flexbox/columndrop.html).

* [`./flexbox/mostlyfluid.html`](./flexbox/mostlyfluid.html) implements the responsive
mostlyfluid flexbox pattern. At its narrowest viewport the layout is stacked, but as the
layout gets wider the grid pattern starts to appear. Once the layout hits its largest
viewport, instead of expanding, margins are added to the left and the right. Breakpoints are set at `450px`, `550px` and `700px`. Demo can be found [here](http://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/flexbox/mostlyfluid.html). More segments in the mostly fluid layout can be found [here](http://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/flexbox/pattern-mostly-fluid-quiz-blankcss.html).

* [`./flexbox/layoutshifter.html`](./flexbox/layoutshifter.html) implements the
responsive layoutshifter flexbox pattern. At the beginning (width less than 500px)
this layout has the sections stacked on top of one another. Breakpoints at 500px and
600px allow the content to move about. Demo can be found [here](http://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/flexbox/layoutshifter.html).

* [`./flexbox/offcanvas.html`](./flexbox/offcanvas.html) implements the responsive offcanvas flexbox pattern. Instead of stacking content vertically, less frequently
used content (e.g., navigation) off screen only showing them if the screen is large
enough (greater than `300px`). Demo can be found [here](http://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/flexbox/offcanvas.html).

## Building the Home Town App
* [`./Hometown/`](./Hometown) implements the first part of the "Building the Home Town App".
A [viewport](#viewport) was added to the page with an initial scale set. Furthermore,
the css was adjusted so that everything displays in a single column, that has been done
with relative widths `(max-width: 100%)`. Finally, the touch targets on the navigation bar where increased by adding paddings to the <a> tag of the nav class `(padding: 1.5em)`,
resulting in targets greater than the suggested 48 pixels wide and 48 pixels tall.

* [`./Hometown 2`](./Hometown 2) implements the second part of the "Building the Home Town App" with the goal to pick a set of breakpoints and using one of the [flexbox patterns](#flexbox) so that it works across different devices. At `600px` the first breakpoint is applied where the scores and the weather are arranged next to each other. Furthermore, the
hamburger icon dissapears with the navigation bar appearing and the font-size of the header title is increased. In that regard, until `600px` the offcanvas flexbox pattern was implemented with the hamburger icon that lets one to display the navigation bar if required. Finally, the mostly fluid pattern is used at `800px`, limiting the container to `800px` and displaying margins around this container for devices with a greater width.

## Responsive Tables
Tables can force horizontal scrolling when the viewport is overflowed. There are several
techniques to prevent this effect (hidden columns, no more tables, contained tables).
* [`./responsive tables/hiddencolumns.html`](./responsive tables/hiddencolumns.html)
impelements the hidden columns approach where the columns are hidden based on their
importance as the viewport size gets smaller. In this example of baseball scores, only
the short names of the team and the final scores are shown up to a viewport size of 400 pixels. If the viewport exceeds 400 pixels the long names of the teams and the scores of all innings are shown. `display: none` allows the standard cells to be hidden.
