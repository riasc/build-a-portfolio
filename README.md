# Project: Build a Portfolio
## Objective
This project is part of the Full Stack Web Developer Nanodegree of Udacity
with the goal of recreating a provided design mockup.

## Viewport
The viewport defines the area the browser can render content to. Browser report the
width in the number of DIPs (Device Independent Pixels) that is a unit of measurement
that relates pixels to a real distance. Any DIP will take up the same amount of space
on a display regardless of the pixel density of the display. If no viewport is set the
browser renders the page for a screen with `980` pixels. In that regard, the
DPR (Device Pixel Ratio) is the ratio between physical and logical pixels.
If a mobile screen has a resolution of `1920x1080` px with a DPR of 2 the maximum
width of a viewport in CSS pixel is `960`.

`<meta name=“viewport” content=“width=device-width, init-scale=“1”>`



## Files
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

