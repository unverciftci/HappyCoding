---
layout: tutorial
title: Pixel Painter
thumbnail: /examples/p5js/images/images/pixel-painter-7.png
tagline: Turn an image into a digital painting.
sort-key: 1150
meta-title: Pixel Painter - p5.js Example
meta-description: Turn an image into a digital painting.
meta-image: /examples/p5js/images/images/pixel-painter-7.png
tags: [example, p5.js, javascript, images, 🎃]
includeP5jsWidget: false
previousPost: /examples/p5js/
---

This sketch turns an image into a digital painting. Every frame, it chooses a random pixel from the original image, and then draws a dot with that pixel's color.

```
let img;

function preload() {
  img = loadImage('images/bee.jpg');
}
function setup() {
  createCanvas(600, 600);

  // Resize the image so it fits on the screen
  img.resize(width, height);

  noStroke();
}

function draw() {

  // Get the color of a random pixel.
  img.loadPixels();
  const pixelX = random(width);
  const pixelY = random(height);
  const pixelColor = img.get(pixelX, pixelY);

  // Paint that pixel with a circle.
  fill(pixelColor);
  ellipse(pixelX, pixelY, 20, 20);
}
```

[Click here to edit this code in the p5 editor.](https://editor.p5js.org/KevinWorkman/sketches/aDwj3IoHh)

![pixel painter](/examples/p5js/images/images/pixel-painter-8.gif)

![cat](/examples/p5js/images/images/pixel-painter-1.png)
![butterfly](/examples/p5js/images/images/pixel-painter-2.png)
![city](/examples/p5js/images/images/pixel-painter-3.png)
![flower](/examples/p5js/images/images/pixel-painter-4.png)
![tree](/examples/p5js/images/images/pixel-painter-5.png)
![bee](/examples/p5js/images/images/pixel-painter-6.png)

This is part of [p5 spooky sketches printout](http://tinyurl.com/p5-spooky-sketches) I made for [CC Fest](http://ccfest.rocks/) in 2019. That printout contains a bunch of Halloween-themed examples of drawing and image manipulation. Feel free to use it on your own or in a classroom!

# Remix Ideas

- Turn your own image into a painting, and post it on the [Happy Coding forum](https://forum.happycoding.io)!
- Draw squares or triangles instead of circles.
- Instead of using the exact color from the original image, add a bit of randomness to it.
