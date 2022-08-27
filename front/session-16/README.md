# Session16
(1401/06/01)

## Js

- Two major patterns for organizing code (data and behavior) are used broadly across the JS ecosystem: classes and modules.

- A class in a program is a definition of a “type” of custom data structure that includes both data and behaviors that operate on that data. Classes define how such a data structure works.

- a class must be instantiated (with the new keyword) one or more times.

- A program can be built without any class definitions, but it would likely be much less organized, harder to read and reason about, and more susceptible to bugs and subpar maintenance.

- Another aspect inherent to traditional “class-oriented” design, though a bit less commonly used in JS, is “inheritance” (and “polymorphism”).

- The fact that both the inherited and overridden methods can have the same name and co-exist is called polymorphism.

- Inheritance is a powerful tool for organizing data/behavior in separate logical units (classes), but allowing the child class to cooperate with the parent by accessing/using its behavior and data.

- The module pattern has essentially the same goal as the class pattern, which is to group data and behavior together into logical units. Also like classes, modules can “include” or “access” the data and behaviors of other modules, for cooperation sake.

- modules have some important differences from classes. Most notably, the syntax is entirely different.

- from the early days of JS, modules was an important and common pattern that was leveraged in countless JS programs, even without a dedicated syntax.

- The key hallmarks of a classic module are an outer function (that runs at least once), which returns an “instance” of the module with one or more functions exposed that can operate on the module instance’s internal (hidden) data.

- The only observable difference in using modules is the lack of using new, calling the module factories as normal functions.

- ES modules (ESM), introduced to the JS language in ES6, are meant to serve much the same spirit and purpose as the existing classic modules just described, especially taking into account important variations and use cases from AMD, UMD, and CommonJS.

- There’s no wrapping function to define a ESM. The wrapping context is a file. They are always file-based; one file, one module.


## Css

- The content CSS property replaces an element with a generated value. Objects inserted using the content property are anonymous replaced elements.
  - [content](https://developer.mozilla.org/en-US/docs/Web/CSS/content)

- In CSS, a replaced element is an element whose representation is outside the scope of CSS; they're external objects whose representation is independent of the CSS formatting model.
  - [replaced element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element)

## types of content value
 [content:value;](https://estelle.github.io/CSS/generated/#slide8)
1. none/normal
2. `<image>`
3. counter()/counters()
4. string
5. open-qoute/close-qoute
6. no-open-quote/no-close-quote
7. attr(x)

### none
- Acts as display: none; on pseudo-elements
- Basically, gets rid of the generated content if there was any added.
> `content:none;`
### normal
- For `::before` and `::after` it's the same as none
- For ::marker it's as if no content was defined, as if set to initial
- For DOM elements, computes to contents, as if not set at all
> `content:normal`
### content and quote properties
- Quotes are a two step process: definte the quote property, then use open-quote and close-quote as values for the content property.
[qoute and content](content and quote properties)
### image
- [image](https://estelle.github.io/CSS/generated/#slide19)
-  Content is not parsed, so url(attr()) does not work.
### Generated Content: Attribute Values ###
- [attr()](https://developer.mozilla.org/en-US/docs/Web/CSS/attr)
- `content:attr(attrname); `

