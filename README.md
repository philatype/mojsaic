# Mojsaic

Remember ASCII art? It showed us that text can make images. Emoji are a
text-adjacent medium. What if we create art from emoji — is that considered
ASCII art? Introducing Mojsaic. It turns an image into an emoji mosaic.
Every pixel of a downscaled image is matched against a curated emoji palette
and redrawn as the closest-colored emoji, rendered through WebGL with a soft
fisheye lens on zoom — and once the view settles, the mosaic becomes real,
selectable emoji text.

**Live demo:** https://philatype.github.io/mojsaic/

## Use

- **Drop any image** onto the page to mosaic it — everything runs
  client-side; your image never leaves the browser.
- **Scroll** to zoom; **drag the mini-map** to move around. On touch,
  **pinch** to zoom and **drag** to pan.
- **Select the emoji** like text once the view is at rest, and copy them
  as a paste-able emoji grid.
- **Emoji count** sets the grid resolution; **Zoom** sets the frame size.

## How it works

The image is downscaled to the chosen column count, each pixel is quantized
and matched to the nearest emoji by weighted RGB distance, and the resulting
mosaic is drawn to an offscreen canvas. A fullscreen WebGL shader displays it
with pan/zoom as uniforms plus a radial distortion term that GSAP pulses
during zoom. The intro builds the mosaic one emoji at a time — first
occurrence of each distinct emoji pops in from the image center outward,
then the rest flood in — before a fast zoom-out reveals the picture.

## License

[MIT](LICENSE)
