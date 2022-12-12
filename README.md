# Frontend Mentor - NFT preview card component solution

This is a solution to the [NFT preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![](./screenshot.jpg)

- Solution URL: [Frontend Mentor Solution](https://www.frontendmentor.io/solutions/nft-preview-card-component-C7v8B8Vhx5)
- Live Site URL: [GitHub Pages](https://lexsupdev.github.io/NFT-preview-card-component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- SCSS

### What I learned

Turns out that :after on an \<img\> tag simply isn't supported by most browsers. (apparently it is supported by Opera, but not much else)

The best solution I can give you is to either wrap your <img> in a <div> or similar, and put the :after on that, or abandon the <img> tag entirely and use a background-image instead.

```html
<div class="nftCard__imageWrap">
  <img src="images/image-equilibrium.jpg" alt="Cube" class="nftCard__image">
</div>
```
```css
.nftCard__imageWrap {
  position: relative;

  &:hover {

    &:before{ 
      content: "";
      position: absolute;
      width: 100%;
      height: 302px;
      top: 0;
      left: 0;
      background: $cyan;
      border-radius: 10px;
      opacity: 0.3;
    }

    &:after {
      content: "";
      position: absolute;
      width: 48px;
      height: 48px;
      top: calc(50% - 24px);
      left: calc(50% - 24px);
      background-image: url("../images/icon-view.svg");
      background-position: center;
  }
  }
}
```

### Continued development

I think i will add some animation.
### Useful resources

- [https://lildude.co.uk/after-css-property-for-img-tag](https://lildude.co.uk/after-css-property-for-img-tag) - This helped me to understand why pseudo-elements didn't work with img.

## Author

- Frontend Mentor - [@lexsupdev](https://www.frontendmentor.io/profile/LexSupDev)
