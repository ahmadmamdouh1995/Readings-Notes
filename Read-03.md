## flex-direction
the four possible values of flex-direction being shown: top to bottom, bottom to top, right to left, and left to right
This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.


## display
This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

##  order
Diagram showing flexbox order. A container with the items being 1 1 1 2 3, -1 1 2 5, and 2 2 99.
By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container

## flex-grow
two rows of items, the first has all equally-sized items with equal flex-grow numbers, the second with the center item at twice the width because its value is 2 instead of 1.
This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least).

##  flex-wrap
two rows of boxes, the first wrapping down onto the second
By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

## flex-basis
This defines the default size of an element before the remaining space is distributed. It can be a length (e.g. 20%, 5rem, etc.) or a keyword. The auto keyword means “look at my width or height property” (which was temporarily done by the main-size keyword until deprecated). The content keyword means “size it based on the item’s content” – this keyword isn’t well supported yet, so it’s hard to test and harder to know what its brethren max-content, min-content, and fit-content do.

## justify-content
flex items within a flex container demonstrating the different spacing options
This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

##  align-self
One item with a align-self value is positioned along the bottom of a flex parent instead of the top where all the rest of the items are.
This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

##  align-items
demonstration of differnet alignment options, like all boxes stuck to the top of a flex parent, the bottom, stretched out, or along a baseline
This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross axis (perpendicular to the main-axis).


### align-content
examples of the align-content property where a group of items cluster at the top or bottom, or stretch out to fill the space, or have spacing.
This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how justify-content aligns individual items within the main-axis.

Note: this property has no effect when there is only one line of flex items.