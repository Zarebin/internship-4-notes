Selectors Part I
- Overview
- Basic Selectors
- Specifications
- Selectors API
- Brief intro to Specificity
- Global selector
- Relational selectors & combinators
- Attribute Selectors
- UI Pseudo-Class Selectors

# Selector

## Css Selector CheatSheet

[CheatSheet](https://www.dropbox.com/s/h2hni9o1m1di989/CSS%20selectors%20cheatsheet.pdf?dl=0)

## Selector level

[All the selectors](https://estelle.github.io/CSS/selectors/#slide15)

## Selectors API

[Link](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)

## Specificity

![Specifishity](https://specifishity.com/specifishity.png)

[SpeciFISHity](https://estelle.github.io/CSS/selectors/#slide20)

- 1-0-0 : ID selector
- 0-1-0 : Class selector (Also attribute selector & pseudoclass)
- 0-0-1 : Element Selector
- 0-0-0 : The * selector, or global selector, has no weight.
- 0-0-0 : Combinators, like ~, >, and + have no weight.

## Relational selectors & combinators

[estelle-link](https://estelle.github.io/CSS/selectors/#slide27)
[W3schools-link](https://www.w3schools.com/css/css_combinators.asp)

## Attribute Selectors

[W3schools-link](https://www.w3schools.com/css/css_attribute_selectors.asp)
[estelle-link](https://estelle.github.io/CSS/selectors/#slide39)

> Question : n this [question](https://estelle.github.io/CSS/selectors/#slide37) why are all of the "a" elements red?
  Response : Attribute target in "a" element is a case of insensitivity, For this reason, the small and large letters do not matter to it
