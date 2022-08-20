#session12
(1401/05/26)


## css selectors partIII

### Pseudo elements
  1. Pseudo-classes select elements that already exist.
  2. Pseudo-elements create "faux" elements you can style.

- [::first-letter](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)
  - The ::first-letter CSS pseudo-element applies styles to the first letter of the first line of a block-level element, but only when not preceded by other content (such as images     or inline tables).
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide7)

- [::first-line](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line)
  - The ::first-line CSS pseudo-element applies styles to the first line of a block-level element.
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide8)

- [::before](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
  - In CSS, ::before creates a pseudo-element that is the first child of the selected element. It is often used to add cosmetic content to an element with the content property. It
     is inline by default. 
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide11)

- [::after](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
  - In CSS, ::after creates a pseudo-element that is the last child of the selected element. It is often used to add cosmetic content to an element with the content property. It is     inline by default.
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide10)

### Newer pseudo-elements

- [::selection](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection)
  - The ::selection CSS pseudo-element applies styles to the part of a document that has been highlighted by the user (such as clicking and dragging the mouse across text).
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide13)

- [disabling::selection](https://estelle.github.io/CSS/selectors/pseudo.html#slide14)

- [::inactive-selection](https://estelle.github.io/CSS/selectors/pseudo.html#slide15)

- [::spelling-error](https://developer.mozilla.org/en-US/docs/Web/CSS/::spelling-error)
  - The portions of text that have been flagged by the user agent as misspelled.

- [::grammar-error](https://developer.mozilla.org/en-US/docs/Web/CSS/::grammar-error)
  - The portions of text that have been flagged by the user agent as grammatically incorrect.

- [::marker](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker)
  - The bullet, or marker, of a list item. 
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide19)

- [::placeholder](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)
  - The placeholder text in an input field
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide20)

- [::backdrop](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
  - Backdrop is displayed when dialog is opened with dialog.showModal

- [::part()](https://developer.mozilla.org/en-US/docs/Web/CSS/::part)
  - Matches element within a shadow tree that has a matching part attribute.
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide25)

-[::slotted()](https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted)
  - Element placed into slot in an HTML template 
  - [example](https://estelle.github.io/CSS/selectors/pseudo.html#slide26) 
 

 ## js
 
	- The best way to learn JS is to start writing JS.

	- In JS, each standalone file is its own separate program.The reason this matters is primarily around error handling.

	- Many projects use build process tools that end upcombining separate files from the project into a single file to be delivered to a web page.

	- Since ES6, JS has also supported a module format in addition to the typical standalone JS program format. Modules are also file-based.JS treat each module separately.

	- The most fundamental unit of information in a program is a value.

	- Values come in two forms in JS: primitive and object.

	- We can use {", 'and `} characters to delimit the string value.

	- The `-delimited string resolves the variable expression (indicated with ${...}) to its value. This is called interpolation.

	- The other primitive values are: boolean , null , undiefined , number and symbol
