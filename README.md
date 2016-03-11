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

Let's use the following sprite as an example:

<img src="http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/css-sprite-example.png" alt="sprite">

This graphic has a total pixel size of 700px x 200px. Lets figure out the size of a single tile (cell). There are 7 icons across so 700 / 7 equals 100 pixels. There are 2 rows, so 200 / 2 equals 100 pixels. This means that a single tile of our grid is a 100px x 100px square. Great so now we just need to create an html element to stick the sprite into.

```html
<a class="facebook-icon" href="#">Facebook</a>
```
Here we gave the a link element a class of `twitter-icon` and put the text inside of it that says "Twitter". Soon we will be replacing this text with an image. Next let's set its width and height to be the size of one tile and set its background property to load the entire sprite image inside of our element.

```css
.facebook-icon {
    display: block;
    width: 77px;
    height: 77px;
    background: url(css-sprite-example.png) no-repeat;
    text-index: 100%;
    overflow: hidden;
    wrap: no-wrap;
}
```



### Rollovers

...

## Summary

- ...

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1M9YKGyk3ivguZBOrExrywmQYId9lmjrrxqAfgdqd58Y/edit?usp=sharing)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-sprite-rollovers' title='Sprite Images and Rollovers'>Sprite Images and Rollovers</a> on Learn.co and start learning to code for free.</p>
