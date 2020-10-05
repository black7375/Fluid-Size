# Fluid Size

[![GitHub Workflow CI  Status](https://img.shields.io/github/workflow/status/black7375/Fluid-Size/CI)](https://github.com/black7375/Fluid-Size/actions?query=workflow%3ACI)
[![GitHub Workflow Publishing Status](https://img.shields.io/github/workflow/status/black7375/Fluid-Size/Publishing?label=Publishing)](https://github.com/black7375/Fluid-Size/actions?query=workflow%3APublishing)
[![npm](https://img.shields.io/npm/v/fluid-size?color=%23CC3534&logo=npm)](https://www.npmjs.com/package/fluid-size) 
[![gpr](https://img.shields.io/github/v/release/black7375/Fluid-Size?color=%23117FFF&label=GPR&logo=github)](https://github.com/black7375/Fluid-Size/packages/336258)

![Fluid-Size](https://raw.githubusercontent.com/black7375/Fluid-Size/resource/resource/Fluid-Size.png)

:triangular_ruler::iphone::computer::desktop_computer: A method of fluidly resizing in various devices based on [`visual angle`](https://en.wikipedia.org/wiki/Visual_angle). (with SASS) :revolving_hearts: :eyes:

Get away from the effects of devices' ***distance***, ***size***, and ***resolution***!!

![fluid-font-size](https://user-images.githubusercontent.com/25581533/82766346-d8f63900-9e0d-11ea-9b3b-ceabd7832e4b.png)
- [Demo(Codepen)](https://codepen.io/black7375/pen/xxZoyow?editors=1100)
- [Demo(Simple ToDo App)](https://black7375.github.io/React-RxJS-Todo/)

## Advantages

[Wiki:Comparison](https://github.com/black7375/Fluid-Size/wiki/Comparison)

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
  @include property($size);
}
```

**Example**

You can use the regular CSS as it is.
There are no restrictions. [Ver 1.5.0 will patch for `%`, `num`]
```scss
// Only Single Value
body {
  @include font-size(16px);       // Countable Value    => Calculated
  @include text-indent(inherit);  // Uncalculated Value => Passed
}

// List Value
body {
  @include font-size(16px !important);         // with Uncountable Value
  @include text-indent(5em hanging each-line); // with Multiple Uncountable Values
  @include margin(-3px 1% 0 auto);             // with Mixed Value
}
```

 **Converted Sample**

```scss
// Code
body {
  @include font-size(16px);
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
body {                       // Default
  font-size: 1rem;
}

@media (min-width: 480px) {  // Phone ~ Tablet
  body {
    font-size: calc(-0.9504790795vw + 1.4567984055rem);
  }
}

@media (min-width: 768px) {  // Tablet ~ Laptop
  body {
    font-size: calc(0.1404102228vw + 0.9331715404rem);
  }
}

@media (min-width: 1280px) { // Laptop ~ Desktop
  body {
    font-size: calc(0.1306874648vw + 0.9409497468rem);
  }
}

@media (min-width: 1920px) { // Desktop ~ High-Desktop, Keep going.
  body {
    font-size: calc(0.5082290299vw + 0.4878998687rem);
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
  @include property($size, $max-size);
  // or
  @include property($size, (option1: value1, option2: value2));
}
```

You can customize resizing method, result's unit, min or max size, ..etc.

 **Converted Sample**

```scss
// Code
body {
  @include font-size(16px !important, (unit: px, max: 25px));
}

// Result
body {                       // Default
  font-size: 16px !important;
}

@media (min-width: 480px) {  // Phone ~ Tablet
  body {
    font-size: calc(-0.95048vw + 23.30877px) !important;
  }
}

@media (min-width: 768px) {  // Tablet ~ Laptop
  body {
    font-size: calc(0.14041vw + 14.93074px) !important;
  }
}

@media (min-width: 1280px) { // Laptop ~ Desktop
  body {
    font-size: calc(0.13069vw + 15.0552px) !important;
  }
}

@media (min-width: 1920px) { // Desktop ~ High-Desktop, Keep going.
  body {
    font-size: calc(0.50823vw + 7.8064px) !important;
  }
}

@media (min-width: 3383px) { // Reach maximum size
  body {
    font-size: 25px !important;
  }
}
```

## Learn More
[Wiki:The theory of font size and readability](https://github.com/black7375/fluid-size/wiki/The-theory-of-font-size-and-readability)

### Principle

Use visual angles to determine the `fit size`(I called) for each device.

![view-distance](https://user-images.githubusercontent.com/25581533/82766340-cc71e080-9e0d-11ea-8268-7c965e6544c0.jpeg)
source: [Legibility: how to make text convenient to read](https://uxdesign.cc/legibility-how-to-make-text-convenient-to-read-7f96b84bd8af)

### Calculation process

1. Size specification
2. Measure the `angle` to be viewed on the [reference device](https://github.com/black7375/Fluid-Size/wiki/API#2-device)
3. Generate a `fit size` for each device based on the `angle`
4. Provides **real-time resizing(fluidity)** for mid-range devices

## Browser Supports

- [CSS3 Media Queries](https://caniuse.com/#feat=css-mediaqueries)
- [`vw` unit](https://caniuse.com/#feat=mdn-css_types_length_vw)([Viewport units](https://caniuse.com/#feat=viewport-units))
- [`calc()`](https://caniuse.com/#feat=calc)
