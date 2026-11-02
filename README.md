# Cloud & Rain Animation

A cloud with falling raindrops built with pure HTML and CSS, no JavaScript. Created as practice with CSS animations, custom properties and pseudo-elements.

## Preview

A white cloud floats on a light blue background. Twenty raindrops fall from it at different speeds, and each one shrinks and disappears when it reaches the ground line.

## How it works

- The cloud is a rounded white block. Its two bumps are drawn with a single `.cloud::before` pseudo-element, where `box-shadow` creates the second circle.
- The rain is a flex container with twenty `<span>` elements, one per drop.
- Each drop gets its own `--seconds` custom property in the HTML. The CSS turns it into the animation duration with `calc(15s / var(--seconds))`, so the drops fall at different speeds without extra rules.
- A single `@keyframes` animation moves a drop down with `translateY()`, then scales it to 0 at the end, so it vanishes on the ground line.

## Usage

Clone or download the repo and open `index.html` in a browser.

```
cloud-rain-drops-animation/
├── index.html
└── style.css
```

## Customization

In `style.css` you can tweak:

- the `15s` value in `animation-duration` to make the rain faster or slower overall
- `translateY()` in `@keyframes rain` to change how far the drops fall
- `width` and `height` on `span` to change the drop size
- `background` on `body` and `.cloud` to change the colors
- the number of `<span>` elements in the HTML, each with its own `--seconds` value
