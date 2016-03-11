# Sprite Images and Rollovers

## Overview

In this lesson we will explore how to create mouse rollover images using sprites.

## Objectives

1. What are sprites?
2. How to determine size and grid position changes
3. Using CSS background-posiition property to adjust sprite position on hover.

## Creating Rollovers With Sprites

<iframe width="100%" height="480" src="//www.youtube.com/embed/Jr6Yhk6IPDA?rel=0" frameborder="0" allowfullscreen></iframe>

*Note: Slides for this lecture video are provided in the resources at the bottom of this lesson.*

### Sprites

What the heck is a sprite? Is it the cousin of a pixie or fairy perhaps? Well no, actually a sprite is simply when as sequence of image frames are included into a single image. For example if you had an icon with two states regular and hover so that the icon visually changes on hover. These two states would be included into a single image file. Then we can use CSS background-position to reposition the image to display the correct state within our element. The advantages to using a sprite are that we can make a single browser request to the get the image file and then we are able to reposition the image almost instantly without having to load more images. Sprites have long been used in the video gaming industry, in native computer applications, and also on the web. They are commonly used on websites for icons and navigation bars among others. If you are handy in an image editor like Photoshop for example you can easily create sprites by building an exact grid and places each image state on a separate equally sized tile of the grid. You can also download sprites other prople make an share. It is important to know the size of an individual tile (or cell) of the grid used for the sprite. Write down these numbers as they will be needed to reposition the sprite using CSS. To get the size required to properly shift the sprite states, in most image editors you can use a ruler tool or you can temporarily crop the sprite to the size of a single state and look at its individual image size. 

### Rollovers

Rollovers are images that change state on mouse over. Let's use the following sprite as an example:

<img src="http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/css-sprite-example.png" alt="sprite">

This graphic has a total pixel size of 700px x 200px. Lets figure out the size of a single tile (cell). There are 7 icons across so 700 / 7 equals 100 pixels. There are 2 rows, so 200 / 2 equals 100 pixels. This means that a single tile of our grid is a 100px x 100px square. Great so now we just need to create an html element to stick the sprite into.

```html
<a class="facebook-icon" href="#">Facebook</a>
```
Here we gave the a link element a class of `facebook-icon` and put the text inside of it that says "Facebook". This text will be useful for search engines, but soon we will be hiding this text and instead showing our icon  image. Next let's set its width and height to be the size of one tile and set its background property to load the entire sprite image inside of our element.

```css
.facebook-icon {
    display: block;
    width: 100px;
    height: 100px;
    background: url(css-sprite-example.png) no-repeat;
    text-indent: 100%;
    overflow: hidden;
    wrap: no-wrap;
}
```

The code above sets the link to display block so we can give it a width and height that matches a tile of our grid 100px x 100px. Then we set its background image to load our sprite. Then to hide the text wihtin out element we set it to indent 100% pushing it outside the width of our element then by setting the overflow to hidden the text disappears. We also set the wrap to no-wrap so there is no danger of the text wrapping below and appearing anywhere inside our element.

<a href="#" onclick="return false;" style="display:block;width:100px;height:100px;background:url(http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/css-sprite-example.png) no-repeat;text-indent: 100%;overflow:hidden;wrap:no-wrap;">Facebook</a>

At this point our image appears in our element. You'll notice that the default positioning for background images is to align the top left corner of the image into the top left corner of our element showing the initial state of our Facebook icon. The rest of the sprite is cropped and out of view.

Now we just need to reposition the sprite on hover,

```css
.facebook-icon:hover {
  background-position: 0 -100px;
}
```

Here we set the `background-position` property to reposition our background image wihtin out element. The first value is for horizontal shift this we set to 0. The second value is for vertical shift which we want to pull the image upward 100px so we set it to -100px. Positive numbers push the image down and to the right, negative numbers pull the image up and to the left. As mentioned the first value moves the sprite horizontally and the second value moves it vertically. Here is our finished example go ahead and hover over the rollover below,

<a class="facebook-icon" href="#" onclick="return false;">Facebook</a><style>.facebook-icon{display:block;width:100px;height:100px;background:url(http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/css-sprite-example.png) no-repeat;text-indent:100%;overflow:hidden;wrap:no-wrap;}.facebook-icon:hover{background-position: 0 -100px;}</style>

## Summary

- ...

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1M9YKGyk3ivguZBOrExrywmQYId9lmjrrxqAfgdqd58Y/edit?usp=sharing)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-sprite-rollovers' title='Sprite Images and Rollovers'>Sprite Images and Rollovers</a> on Learn.co and start learning to code for free.</p>
