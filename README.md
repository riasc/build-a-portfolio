# Project: Build a Portfolio
## Objective
This project is part of the [Full Stack Web Developer Nanodegree](https://de.udacity.com/course/full-stack-web-developer-nanodegree--nd004/)
with the goal of recreating a [design mockup](design-mockup-portfolio.pdf). The final solution can be found [here](./mockup) with a live demo
[here](http://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/mockup/index.html).



##
HTML (Hyper Text Markup Language) is the standard markup language for describing the structure of web pages.
Its elements are the building blocks of HTML pages and represented by tags that label pieces of content such
as 'heading', 'paragraph', 'table'. Browser do not display the HTML tags, but use them to render content of
the page. CSS (Cascading Style Sheets) describes how HTML elements are to be displayed on screen, paper,
or in other media.

## Frameworks
Frameworks are collections of CSS classes that make page layout easy to implement.



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
The point at which the page changes layout significantly is called a major breakpoint.
Similar, minor breakpoints are only small changes to the layout (padding, margins, font size).


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
resulting in targets greater than the suggested 48 pixels wide and 48 pixels tall. Demo can be found [here](https://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/Hometown/index.html).

* [`./Hometown 2`](./Hometown 2) implements the second part of the "Building the Home Town App" with the goal to pick a set of breakpoints and using one of the [flexbox patterns](#flexbox) so that it works across different devices. At `600px` the first breakpoint is applied where the scores and the weather are arranged next to each other. Furthermore, the
hamburger icon dissapears with the navigation bar appearing and the font-size of the header title is increased. In that regard, until `600px` the offcanvas flexbox pattern was implemented with the hamburger icon that lets one to display the navigation bar if required. Finally, the mostly fluid pattern is used at `800px`, limiting the container to `800px` and displaying margins around this container for devices with a greater width. Demo can be found [here](https://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/Hometown%202/index.html)

* [`./Hometown 3`](./Hometown 3) implements the final part of the "Building the Home Town App" with the goal of updating the sports table with the favorite team, breaking up the
text if necessary, including minor breakpoints and include responsive images. The score
table was updated with the last results of the football team from cologne. Setting
`font-size: 14px; line-height: 1.2em;` in the content class applied the increased
font-size for all the text on the page and improved its readability. Furthermore, minor breakpoints were applied to the weather section `(font-weight: bold; font-size: 5em;)`.
Weather icons were replaced by responsive ones. Demo can be found [here](https://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/Hometown%203/index.html)

## Responsive Tables
Tables can force horizontal scrolling when the viewport is overflowed. There are several
techniques to prevent this effect (hidden columns, no more tables, contained tables).
* [`./responsive tables/hiddencolumns.html`](./responsive tables/hiddencolumns.html)
implements the hidden columns approach where the columns are hidden based on their
importance as the viewport size gets smaller. In this example of baseball scores, only
the short names of the team and the final scores are shown up to a viewport size of 400 pixels. If the viewport exceeds 400 pixels the long names of the teams and the scores of all innings are shown. Cells can be hidden with the property `display: none`. However, the
problem with this approach is that on smaller viewports the data is hidden completely. Needs to be applied with caution and if possible abbreviated data should used.
Demo can be found [here](https://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/responsive%20tables/hiddencolumns.html).

* [`./responsive tables/nomoretables.html`](./responsive tables/nomoretables.html) implements the no more tables technique where below a certain viewport width the
table is collapsed and resembles a long list as opposed to a table data, allowing to
display the whole data, no matter what the size of the viewport is. In a wider viewport
(> 500 pixels) the whole table is visible, but as the viewport shrinks the table collapses
where every column becomes its own row with the table header beside it. Demo can be found [here](https://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/responsive%20tables/nomoretables.html).

* [`./responsive tables/containedtable.html`](./responsive tables/containedtable.html) implements the contained table technique where the table will take up the same width as the
viewport, but will scroll within the viewport. The tables only has to be wrapped inside a div with `width: 100%` and `overflow-x: auto`. Demo can be found [here](https://htmlpreview.github.io/?https://github.com/riasc/build-a-portfolio/blob/master/responsive%20tables/containedtable.html).

## Fonts
Ideal measure of the length of a line for the web lies around 65 characters per line (cpl).
This needs to be taken into consideration when choosing the breakpoints. Fonts need to be
big enough to read across any device.

```css
.goodfont {
    font-size: 16px;
    line-height: 1.2em;
}
.biggerfont {
    font-size: 18px;
    line-height: 1.25em;
}
```

## Responsive Images
"Create a product, don't re-imagine one for small screens. Great mobile products are created, never ported" - Brian Fling. Total file size depends on the number of pixels multiplied by the number of bits to store one pixel. For the improvement of the performance, images need to be as small as possible and compression as high as possible.
This is supported by the fact, that the average webpage makes 56 requests for images.
Each of these requests has a cost in page load where even small delays in pages can
have a significant loss in traffic and revenue for that page.

### Sizing

With fixed image size (e.g., natural size of the image) resizing the window will cause cropping of the image and on mobile devices the image could end up being larger than the viewport, which means that in order to see the whole image one would have to scroll horizontally. When using relative sizing `(width: 100%)` it looks good in the smaller
browser windows and on mobile devices, but the window is resized the image gets blurry.
If `max-width: 100%` will only expand as wide as its natural width. Relative sizing also
helpful when two images need to be places side by side.
```css
img {
    width: 50%;
}
```
When there should be a 10% margin between the images, absolute and relative values need to be combined where `calc` comes in handy.
```css
img {
   margin-right: 10px;
   width: calc((100%-10px)/2);
}
```
Furthermore, the `img:last-of-type` selector to ensure that there is only a margin between the images and none to the right of the second image.
```css
img:last-of-type {
    margin-right: 0;
}
```
An image can responsively cover the whole height of the viewport. Obviously this can
be done by setting `height: 100%`, but that only works if the height of the html and
the body elements are also set to 100%. A simple way is to use the vh-unit,
that stands for "viewport height". One vh corresponds to one percent of viewport height,
so `height: 100vh` means 100% height. Similarly, the vw can be applied for "viewport width".
Another common responsive use case is when an image should resize to fit the smaller of height or width of the viewport. The vmin unit (viewport minimum) corresponds to one percent of the viewport width or height (whichever is smaller). Setting
`width: 100vmin; height: 100vmin;` will get this effect. If an image should cover the whole
viewport without stretching or squashing the vmax unit can be applied. Its corresponds to one percent of the viewport width or height (whichever is greater). Setting
`width: 100vmax; height: 100vmax;` the image responsively resizes to cover the viewport.

The property `background-size` specifies the size of the background images. Setting
`background-size: cover` ensures that the image is sized so that it is as small as possible
while still completely filling its container. Likewise, `background-size: contain` ensures
that the image is sized so that it is as large as possible while still being completely
visible inside its container.

There are two ways to store image responsively - raster and vectors. Raster images are
photographs and images that are represented as a grid of individual dots of color. These images may come from camera or scanner and will be created with the html canvas elements.
Vector images are logos that can be defined as a set of curves, lines, shapes, fill colors and gradients. Can be created by Inkscape or Adobe Illustrator or by using a vector
format such as svg (scalable vector graphic) that makes it possible to include
responsive vector graphics in a webpage. The advantage of the vector file formats
over raster file formats is that the browser can render a vector image at any size.
After all vectors graphics describe the geometry of the image and not the individuals
dots of color.

Latency - delay between request and response. Number of file request can be just as
significant as the size of the file requests. Latency is the new bottleneck. SVG and
DataURI can inline images and thus reduce the number of file requests. DataURI provide
a way to include a file (e.g., image) inline as a base 64 encoded string using
`<img src="data:image/svg+xml:base64,[data]">`.

Serving the right image for every combination of device capabilities and display size is
important. A problem with media queries is that they only refer to the viewport dimensions
and not the actual display size of the image. Providing alternative files via sourceset
for the same image allow the browser to choose the best option for the viewport size and
device capabilities. There are two flavors of srcset, one using x to differentiate between
device pixel ratios (DPR), and the other using w to describe the image's width.

#### Reacting to Device Pixel Ratio
```html
<img src="image_2x.jpg" srcset="image_2x.jpg 2x, image_1x.jpg 1x" alt="a cool image">
````
Set srcset equal to a comma separated string of filename multiplier pairs, where each
multiplier must be an integer followed by an x. For example, 1x represents 1x displays
and 2x represents displays with twice the pixel density, like Apple's Retina displays.
Different screens have different pixel densities, more or less dots of color per square inch,
the physical pixels. It can be read out through `window.devicePixelRatio`. The browser will
download the image that best corresponds to its DPR
([Pixel Density (PPI) List](http://pixensity.com/list/)). Also, note that there's a src
attribute as a fallback.

#### Reacting to Image Width
```html
<img src="image_200.jpg" srcset="image_200.jpg 200w, image_100.jpg 100w" alt="a cool image">
```
Set srcset equal to a comma separated string of filename widthDescriptor pairs, where each widthDescriptor is measured in pixels and must be an integer followed by a w. Here, the widthDescriptor gives the natural width of each image file, which enables the browser to
choose the most appropriate image to request, depending on viewport size and DPR.
(Without the widthDescriptor, the browser cannot know the width of an image without downloading it!)
Also, note that there's a src attribute as a fallback.

#### Image Width with sizes
What if the image won't be displayed at the full viewport width? Then you need something more than srcset, which assumes the image will be full viewport width.

Add a sizes attribute to the image with a media query and a vw value. srcset and sizes together tell the browser the natural width of the image, and how wide the image will be displayed relative to viewport width. Knowing the display width of the image and the widths of the image files available to it, the browser has the information it needs to download the image with the right resolution for its needs that is as small as possible. And it can make this choice early in the page load while the HTML is still being parsed.

```html
<img  src="images/great_pic_800.jpg"
      sizes="(max-width: 400px) 100vw, (min-width: 401px) 50vw"
      srcset="images/great_pic_400.jpg 400w, images/great_pic_800.jpg 800w"
      alt="great picture">
```

`sizes` consists of comma separated `mediaQuery width` pairs. `sizes` tells the browser early in the load process that the image will be displayed at some `width` when the `mediaQuery` is hit.
In fact, if `sizes` is missing, the browser defaults `sizes` to `100vw`, meaning that it expects the image will display at the full viewport width. `sizes` gives the browser one more piece of information to ensure that it downloads the right image file based on the eventual display width of the image. Just to be clear, it does not actually resize the image - that's what CSS does.

In this example, the browser knows that the image will be full viewport width if the browser's viewport is 400px wide or less, and half viewport width if greater than 400px. It knows that it has two image options - one with a natural width of 400px and the other 800px.

The picture element is a way to provide alternative sources for images files, such that the
browser can choose depending on device capabilities.
```html
<picture>
    <source srcset="image.webp" type="image/webp"></source>
    <source srcset="image.jpg" type="image/jpeg"></source>
    <img src="image.jpg" alt="title">
</picture>
```
This also allows for art direction - to choose different images. In this case `<img>` acts as a fallback, meaning that if no sources gets hit the image in this
tag will be displayed. Also for browsers that don't support picture, the image will be displayed by default.
```html
<picture>
    <source media="min-width: 650px" srcset="large.jpg"></source>
    <source media="min-width: 465px" srcset="medium.jpg"></source>
    <img src="small.jpg" alt="title">
</picture>
```
As not all browser support the picture element, [picturefill](http://scottjehl.github.io/picturefill/) can be used to mimic this effect. Images are not accessible to everyone to the same extent. Nevertheless, sites need to be reasonable even without images as with screen readers
(e.g., [chromeVOX](http://www.chromevox.com/)) by using the `alt` attribute responsibly.