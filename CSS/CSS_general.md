# CSS positioning and the box model
Usefull link: https://learn.shayhowe.com/advanced-html-css/performance-organization/ 

## Tips 
- Different positioning (static, relative, absolute, fixed, or sticky)
    - Fixed: The element is positioned relative to the browser window
    - Absolute: The element is positioned relative to its first positioned (not static) ancestor element
    - Relative: The element is positioned relative to its normal position, so "left:20px" adds 20 pixels to the element's LEFT position
    - Static: Default value. Elements render in order, as they appear in the document flow
    - Sticky: The element is positioned based on the user's scroll position
- Inherit: Inherits this property from its parent element
- Z-index: Lets you place elements on top of eachother. (stacking order)
- Float:roperty specifies whether an element should float to the left, right, or not at all.

*** Box model ***
- Border, margin and padding.
- Vertical margins collapse: so 5 and 5 is not 10 margin but 5 margin when there are two elements.

***Display***
- Inline, inline-block, block

*** styling text ***
- Different fonts and their collections. Sans-serif, serif, cursive, monospace etc.
- Font family needs to be available at the pc of the client.
- Font-familiy: first choice, second choice, last choice;
- DO NOT USE PIXEL. Em and Rem are better for accessibility. 
- Text properties: TExt-indent, letter-spacing, word-spacing, text-decoration, text-align, text-transform, vertical-align.


*** CSS Reset ***
- This is a sheet that will great a starting point for styling. This way the css isnt dependent on the different browsers/


## own opinion
I feel like positioning and float are outdated. Flexbox and css grid are more versetail and evolved. It is good to know legacy when you encounter it.