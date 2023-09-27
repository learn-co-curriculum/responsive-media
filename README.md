# Intro to Responsive Media

## Learning Goals

- Explain responsive layouts.
- Use percent measurements.

## Introduction

Media queries allow us to choose between certain styles based on the size of
the device. We can easily imagine a web page full of text breaking into
multiple columns on wide screens and reducing to a single screen on a phone.
But what about _media_ instead of text? How can we make sure that a photo of an
adorable kitten makes sense in a multi-column _and_ a single-column display?

> **NOTE:** We're going to talk about _media_ as in images or videos in this
> lesson. Don't confuse _media_ with _media queries_.

## Explain Responsive Layouts

To quote Bruce Lee:

> "You must be shapeless, formless, "like water". When you pour water in a
cup, it becomes the cup. When you pour water in a bottle, it becomes the
bottle. When you pour water in a teapot, it becomes the teapot.  Water can drip
and it can crash. Become like water my friend."

With CSS, we can create _fluid_ content. Using percent (%) measurements on our
media's CSS allows them to fluidly fill the size of their container. In most
cases our media is contained within the columns and rows of our layouts.

<iframe width="640" height="480" src="//www.youtube.com/embed/iC2yQbR_qys?rel=0&modestbranding=1" frameborder="0" allowfullscreen></iframe>

## Use Percent Measurements

```css
img, form, input, table, video, audio, iframe {
  width: 100%;
}
```

In this code snippet, we set our images, forms, inputs, tables, videos, audio
elements, and iframes all to expand `width: 100%;`. This sets them to be as
wide as the parent element they are inside of. 

```css
img, form, input, table, video, audio, iframe {
  max-width: 100%;
}
```

In this code snippet, we set our images, forms, inputs, tables, videos, audio 
elements, and iframes all to expand to `max-width: 100%`. For media that is 
larger in size than its parent element, this will behave exactly the same as 
setting `width: 100%`, i.e. the media will fill the parent's width no matter 
what. However, if the media's original width is smaller than the width of the 
parent, it will not expand to fill the parent's width when the parent's width is 
larger than the media. For example, if the parent is 500px wide and we are 
displaying an image that is 300px wide, that image will not be scaled any larger 
than 300px wide. When the parent element is 300px wide or smaller, the image 
will fill the parent. This prevents pixelation of images.

Using these properties ensures that our media scales fluidly and allows us to 
write fewer media queries. We can focus on sizing the parent element of the 
media content, instead of manually sizing each element.

Consider a website like [Instagram](https://instagram.com): each photo being displayed
to a user shares a 'column' of content - a username, the photo, likes, comments;
all fit into the width of a 'card' on the page. If the card shrinks or expands
in size, the photo will too. Users on different sized screens will see a web
page that is _slightly_ different, but at all sizes, the content looks good and
is nearly consistent.

## Conclusion

In order to scale content to fill a container, we can set our media's width
properties to `width: 100%; max-width: 100%;`. They'll have flexible, fluid
widths that will expand to the size of their parent in proportion. It will
resize to accommodate the device automatically in most cases. It keeps sites
accessible and the code more maintainable with fewer media queries.

## Resources

- [Responsive Media Content - Code Example](http://jsfiddle.net/flatiron_school/HP6A3/1/)
