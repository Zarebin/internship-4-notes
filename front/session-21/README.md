# Session-21
(1401-06-13)

## Js

### Concise Properties
-When defining an object literal, it's common to use a property name that's the same as an existing in-scope identifier that holds the value you want to assign.

`
coolFact = "the first person convicted of speeding was going 8 mph";

anotherObj = {
    coolFact: coolFact
};
`

-In this situation, where the property name and value expression identifier are identical, you can omit the property-name portion of the property definition, as a so-called "concise property" definition:

`coolFact = "the first person convicted of speeding was going 8 mph";

anotherObj = {
    coolFact   // <-- concise property short-hand
};
`
### Concise Methods
Another similar shorthand is defining functions/methods in an object literal using a more concise form:

`
anotherObj = {
    // standard function property
    greet: function() { console.log("Hello!"); },

    // concise function/method property
    greet2() { console.log("Hello, friend!"); }
};
`
- generator functions:

`
anotherObj = {
    // instead of:
    //   greet3: function*() { yield "Hello, everyone!"; }

    // concise generator method
    *greet3() { yield "Hello, everyone!"; }
};
`

[link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*)
[link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator)

- concise methods/generators can even have quoted or computed names:
`
anotherObj = {
    "greet-4"() { console.log("Hello, audience!"); },

    // concise computed name
    [ "gr" + "eet 5" ]() { console.log("Hello, audience!"); },

    // concise computed generator name
    *[ "ok, greet 6".toUpperCase() ]() { yield "Hello, audience!"; }
};
`
### Object Spread

[shallow copy vs deep copy](https://code.tutsplus.com/articles/the-best-way-to-deep-copy-an-object-in-javascript--cms-39655)

- Another way to define properties at object literal creation time is with a form of the ... syntax
- The ... when used inside an object literal will "spread" out the contents (properties, aka key/value pairs) of another object value into the object being defined:


`
anotherObj = {
    favoriteNumber: 12,

    ...myObj,   // object spread, shallow copies `myObj`

    greeting: "Hello!"
}
`

- The spreading of myObj's properties is shallow, in that it only copies the top-level properties from myObj; any values those properties hold are simply assigned over. If any of those values are references to other objects, the references themselves are assigned (by copy), but the underlying object values are not duplicated -- so you end up with multiple shared references to the same object(s).

### Deep Object Copy

- Also, since ... doesn't do full, deep object duplication, the object spread is generally only suitable for duplicating objects that hold simple, primitive values only, not references to other objects.

-  For deep object duplication, the standard approaches have been:
 1- Use a library utility
 2- Use the JSON.parse(JSON.stringify(..))



## Css
 
### Media Queries

#### Display, Color & Interaction features

- Pointer : Is the primary input mechanism a pointing device, and if so, how accurate is it? none | coarse | fine
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/pointer)
- Hover : Does the primary input mechanism allow the user to hover over elements? none | hover
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/hover)
- Any-pointer : Is any available input mechanism a pointing device, and if so, how accurate is it? none | coarse | fine
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-pointer)
- Any-hover : Does any available input mechanism allow the user to hover over elements? none | hover
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-hover)
- Grid : Does the device use a grid (i.e. TTY) or bitmap screen? 0 | 1 or (grid)
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/grid)
- Color : of bits per color component. Zero if device isn't color. @media (min-color: 1) means it's a color device
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color)

### Additional Media Features

- Color-gamut :Approx. range of supported colors. srgb | p3 | rec2020 (Ch,Op,Sf)
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-gamut)
- Display-mode : The display mode of the application, as specified in the web app manifest's display member (Defined in the Manifest Spec) full-screen | standalone | minimal-ui | browser (Ch,Op,FF)
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/display-mode)
- Monochrome : Bits per pixel in the output device's monochrome frame buffer, or 0 if the device isn't monochrome (FF,Ch,Op,Sf)
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/monochrome)
- Overflow-block : How is content that overflows the block axis handled? none | scroll | optional-paged | paged (FF)
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/overflow-block)
- Overflow-inline : Can content that overflows the viewport along the inline axis be scrolled? (FF)
 - [example](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/overflow-inline)

### Unsupported Media Features

- Scan : Scanning process of the output device/ interlace | progressive
- Update : Frequency capability of content modification appearance. none | slow | fast
- Color-index : Number of entries in the color lookup table. (color-index) | (min|max-color-index: n)
- Inverted-colors : Are colors being inverted. none | inverted
- Light-level : Light level of the environment. dim | normal | washed
- Scripting : Tests whether scripting (JS) is available. none | initial-only | enabled


