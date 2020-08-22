# Fluid Size

![Logo](https://user-images.githubusercontent.com/25581533/90948604-eda79480-e42f-11ea-836e-1472bdb0d75b.png)

:desktop_computer: :computer::iphone: A method of fluidly resizing in response to various devices. (with SASS) :revolving_hearts: :eyes:

It is a way to respond to the distance between the eye and the device, the size and resolution of the device.

![fluid-font-size](https://user-images.githubusercontent.com/25581533/82766346-d8f63900-9e0d-11ea-9b3b-ceabd7832e4b.png)
- [Demo(Codepen)](https://codepen.io/black7375/pen/xxZoyow?editors=1100)
- [Demo(Simple ToDo App)](https://black7375.github.io/React-RxJS-Todo/)

## Advantages
- Easy
- Provides the `fit size` for each device
- Resized `fluidly` between each device
- Compatible with [include-media](https://github.com/eduardoboucas/include-media)

## How to Use?

### Install

```shell
## Yarn
yarn add fluid-size

## NPM
npm install fluid-size

## Github Repository
npm install @black7375/fluid-size
```

### Import

```scss
@import '~fluid-size/fluid-size';
```

### Usage

Just use the name of the [API](https://github.com/black7375/fluid-size/wiki/API) with `@include`!!

```scss
tag {
  @include property($size-value, $max-size-value);
  // or
  @include property($size-value, $options);
}
```

 **Converted Sample**

```scss
// Code
body {
  @include font-size(16px !important, (unit: em, device: min, max: 25px));
}

/** Tentative Result
 * INFO
 * Basis Angle: min angle device(Tablet)
 *
 * SIZES
 * Default:            16px;
 * Phone:        about 18.75px;
 * Tablet:       about 16px;
 * Laptop:       about 16.73px;
 * Desktop:      about 17.56px;
 * High-Desktop: about 20.82px;
 */

// Result
body {
  font-size: 1em !important;
}

@media (min-width: 480px) {  // Phone
  body {
    font-size: calc(-0.95048vw + 1.4568em) !important;
  }
}

@media (min-width: 768px) {  // Tablet
  body {
    font-size: calc(0.14041vw + 0.93317em) !important;
  }
}

@media (min-width: 1280px) { // Laptop
  body {
    font-size: calc(0.13069vw + 0.94095em) !important;
  }
}

@media (min-width: 1920px) { // Desktop
  body {
    font-size: calc(0.50823vw + 0.4879em) !important;
  }
}

@media (min-width: 2560px) { // High-Desktop
  body {
    font-size: calc(0.50823vw + 0.4879em) !important;
  }
}

@media (min-width: 3383px) { // Reach maximum size
  body {
    font-size: 1.5625em !important;
  }
}
```

### Options

[Wiki:API(Options)](https://github.com/black7375/fluid-size/wiki/API#options)

Options consist of global and scoped options.

- Global Option: Setting it as a `variable` changes the default value of the whole.
- Scoped Option: It is provided as an argument(`map` type) to the function, and when used, applies only to the current value.

```scss
// Global Option
$option1: value1;
$option2: value2;

// Scoped Option
tag {
  @include property($size, (option1: value1, option2: value2));
}
```

You can customize resizing method, result's unit, min or max size, ..etc.

## Learn More
[Wiki:The theory of font size and readability](https://github.com/black7375/fluid-size/wiki/The-theory-of-font-size-and-readability)

### Principle

Use visual angles to determine the `fit size`(I called) for each device.

![view-distance](https://user-images.githubusercontent.com/25581533/82766340-cc71e080-9e0d-11ea-8268-7c965e6544c0.jpeg)
source: [Legibility: how to make text convenient to read](https://uxdesign.cc/legibility-how-to-make-text-convenient-to-read-7f96b84bd8af)

### Calculation process

1. Size specification
2. Angle calculations in the devices that would look the smallest(or can you specify which device to reference?, [Options:device](https://github.com/black7375/Fluid-Size/wiki/API#2-device))
3. Generate a `fit size` for each device based on the angle
4. Provides fluidity between devices


## Browser Supports

- [CSS3 Media Queries](https://caniuse.com/#feat=css-mediaqueries)
- [`vw` unit](https://caniuse.com/#feat=mdn-css_types_length_vw)([Viewport units](https://caniuse.com/#feat=viewport-units))
- [`calc()`](https://caniuse.com/#feat=calc)
