# CSS
Cascading Style Sheet. CSS follows two patterns; specificity and cascading.

## Cascading
CSS follows a cascading patttern. What this means is that styling lower in the file will take precedence. Look at this example:

```css
  .box {
    background: red;
  }
  .box {
    background: blue;
  }
  .box {
    background: green;
  }
```

What color would our div with a class of `.box` be? Green, because that CSS is the lowest in the file.



## Specificity
CSS also follows what is called specificity. Specificity means that styling will be applied to something that is more specific (or has a higher weight) than something that doesn't. Take a look at this CSS layout:

```css
  #box {
    background: green;
  }

  .box {
    background: red;
  }
```

Here we have to selectors; one ID and one class. Even though the `.box` styling is lower, ID's are more specific (have a higher weight) that classes so the div with a class of `.box` will have a green background.

Here is the specificity of common CSS selectors:

* Elements and pseudo-elements: 1
* Classes, attributes and pseudo-classes: 10
* ID's: 100
* Inline styling: More specific than ID's, no weight
* `!important`: Just don't use it but know that it will override everything other than another `!important`.

## Box Model
CSS has a way of determining how it will display it's contents called the box model. The box Model flows from the outside in like this: margin -> border -> padding -> content.

From the outside in:
* Margin: determines how far away other elemtns will be from it.
* Border: effects the elements overall height and width. Used to create borders.
* Padding: Used to give an element more overall size. This makes the size of the element bigger.
* Content: The actual size of the content. Will take into account height and width if it is styled.

## box-sizing

Box sizing determines how an element will determine it's width while taking into account margin and padding. Most often you will use `box-sizing: border-box` to make elements calcuate their size while taking padding and margin into consideration. If you find that your elements are spilling off of your screen, be sure to check that you have this CSS added to the top of your file.

```css
body, * {
  box-sizing: border-box;
}
```

## Positioning
Know the different values of the CSS `postion` attribute will help you further your ability to create custom layouts. There are 6 values you can use:

* `absolute`: moves an element based on the `top`, `right`, `bottom`, `left` attritubtes. Will default to thhe body as it's parent container unless a parent container contains `position: relative`.

* `relative`: Relative means relative to it's original layout on the screen. This also respects the `top`, `right`, `bottom`, `left` attritubtes given to it. Relative will also be used to control children elements that have `position: absolute`

* `fixed`: Fixed is used to fix itself on the screen at a desired location. Uses the `top`, `right`, `bottom`, `left` attritubtes. You will need to utilize `width: 100%` to stretch a element across the screen, like a navbar.

* `sticky`: Similar to fixed and absolute. Sticky is used to make an element fixed to a certain point and then flow with the page like normal or the exact opposite. Think of a subscribe box on a website that initially starts at the top of the screen and then follows you as you scroll down the screen.

* `initial`: Initial is the elements initial position as dictated by the browser.

* `inherit`: Inherit is used to inherit a parent containers position attribute value. Very rarely should you use this.

## Flex Box
Flex box is a newer way to layout your page. This has mostly replaced the `position` property but it is good to know both. To start using flex box, you will always need to use this property: `display: flex`. This allows the container to flex any items inside of it. There are many different properties you can use with `flex` but the main ones to be aware of are
* `justify-content`
* `flex-direction`
* `align-items`
* `flex-wrap`

All of the above properties have many different possible value. Try setting an element to `display: flex` and then testing out the differenter properties above with their differen values.