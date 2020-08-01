# Fluid Size

:desktop_computer: :computer::iphone: A method of fluidly resizing in response to various devices. (with SASS) :revolving_hearts: :eyes:

It is a way to respond to the distance between the eye and the device, the size and resolution of the device.

![fluid-font-size](https://user-images.githubusercontent.com/25581533/82766346-d8f63900-9e0d-11ea-9b3b-ceabd7832e4b.png)
- [Demo(Codepen)](https://codepen.io/black7375/pen/xxZoyow)
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

Just use the name of the [Wiki:API](https://github.com/black7375/fluid-size/wiki/API) with `@include`!!

```scss
 @include font-size($size-value, $max-size-value);
```

 **Converted Sample**

```scss
// Code
body {
  @include font-size(16px);
}

// Tentative Result
/*
Default:            16px;
Phone:        about 18.75px;
Tablet:       about 16px;
Laptop:       about 16.73px;
Desktop:      about 17.56px;
High-Desktop: about 20.82px;
*/

// Result
@media (min-width: 480px) { // Phone
  body {
    font-size: calc(-0.9504790795vw + 1.4567984055em);
  }
}
@media (min-width: 768px) { // Tablet
  body {
    font-size: calc(0.1404102228vw + 0.9331715404em);
  }
}
@media (min-width: 1280px) { // Laptop
  body {
    font-size: calc(0.1306874648vw + 0.9409497468em);
  }
}
@media (min-width: 1920px) { // Desktop
  body {
    font-size: calc(0.5082290299vw + 0.4878998687em);
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
2. Angle calculations in the devices that would look the smallest(or can you specify which device to reference?)
3. Generate a `fit size` for each device based on the angle
4. Provides fluidity between devices
