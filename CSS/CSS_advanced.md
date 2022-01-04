# CSS advanced

## Tips 
*** Performance and organisation ***
- With CSS at scale organisation is key. Seperating stylesheets is a part of this.
- Object Oriented CSS (OOCSS)
    - Separate structure from skin: includes abstracting the layout of an element away from the theme of a website. 
    - Separate content from container: involves removing the dependency of a parent element nesting children elements. 
- Scalable and modular architecture for CSS (SMACSS)
- performance of the selector. 
    - Classes have good performance so try to use them
    - reusable code
- compression of images and files
- Reduce the http request form the html to css.
`<!-- Bad -->
<link href="css/reset.css" rel="stylesheet">
<link href="css/base.css" rel="stylesheet">
<link href="css/site.css" rel="stylesheet">

<!-- Good -->
<link href="css/styles.css" rel="stylesheet">
`

- image spriting: use one image for multiple backgrounds.
- Image data uri: great for small images
- cache common files

*** Detailed positioning ***
- Overflow, float and cleafix technique
    - Overflow: property specifies what should happen if content overflows an element's box.
    - Float(better use flexbox)
    - cleafix uses before and after pseudo elements.  also used to contain floats.
- Positioning is also mentioned in ccs_general

*** Complex Selectors ***
- Siblings, childs, parents, attribute selectors ( contains, begins, equal)
- Pseudo classes like hover, visited, focus, active
- structural and position pseudo classes
    - :first-child, :last-child etc.
- numeric pseudo selectors :nth-of-type(n) & :nth-last-of-type(n)
- Textual pseudo-elements: First-letter, first-line
- Single colon : vs double colon ::
    - The fragment pseudo-element was added with CSS3 and in attempt to differentiate pseudo-classes from pseudo-elements the double colons were added to pseudo-elements. 
    - pseudo element:  :first-letter
    - pseudo class :link, :hover
- Watchout for the performance and speed of each selector. 

*** Responsive Web design ***
- Responive web design
    - Flexible layouts, media Queries, and flexible media.
- relative lengths like % and em are support even in older browsers
- vw, vh, vmin and vmax are new and not yet support on every browser.
- target ÷ context = result
- The above items are resolved iin flexbox and css grids.

- Media queries -> different styles for each browser and device. @media, @import use @media so there are no additional http requests.
    - use min max prefixes
    - logical operators like not, only and all.
    - orientation: landscape vs portrait
    - aspect ratio of the screen
    - pixel ratio and resolution ratio
    - Identifying Breakpoints  is a bad idea because of the different resolutions on screens.
    - Media queries can reduce the amount of images that need to be loaded into the website.

*** Preprocessors ***
- Preprocessors: A preprocessor is a program that takes one type of data and converts it to another type of data.
- HTML - Haml and CSS - SCSS, Sass
- SCSS vs Sass: Deciding on whether to use SCSS or Sass boils down to personal preference, and is a decision to be made based on what is best for a specific team and project. There are pros and cons to each syntax, all of which are fair.

*** Less ***
- a superset of CSS that adds features to the language. 
    - Variables, functions, operations, nested rules, namespacing and scoping
- Variable interpolation: last setting of the variable is the variables value. 
- prefixes for class names can also be used. 
- Maps (arrays) can also be used in less. @breakpoint[desktop]
- functions like minmax and other functions are available.
- Guards (if statement) are also possible in less
- nesting rules with selectors
- Reusable patterns:
    - Mixins
    - Detached rulesets
    - sharing rules with for instance: .container();

*** JQuery ***
- Jquery: open source javascript library.  Selections resembling CSS and a comprehensible separation of behavior.
- Leading http if not specified than the link can use both methods. (HTTPS is recommended)
- $ sign in JQuery
    $('.feature');           // Class selector
    $('li strong');          // Descendant selector
    $('em, i');              // Multiple selector
    $('a[target="_blank"]'); // Attribute selector
    $('p:nth-child(2)');     // Pseudo-class selector
- You can also filter in the selection keyword: $('div:has(strong))
- you can easiliy manipulate the dom with Jquery. 
- Adding events is easy instead of javascript .addeventlistener
- you can also use css in jquery ( I would still keep them separate)


*** Transforms ***
- Transform can be 2d or 3d. 
- Transform makes it possible to rotate, scale etc html elements
- Perspective, skew, scaleY etc are all properties

*** Transistion and animations ***
- Transition:  allows you to change property values smoothly, over a given duration.
- transition, transition-delay, transition-duration, transition-property,transition-timing-function
- Vendor prefixes
    - For the best browser support use them. 
        - -webkit-, -moz-, -o-
- not all properties of css can be transitioned. They need to have and identifiable halway point. Colors, fonts etc can be transitioned
- Shorthand transitions are nice to reduce the amount of lines, but it reduces readability

- Animations: Transitions do a great job of building out visual interactions from one state to another, and are perfect for these kinds of single state changes. However, when more control is required, transitions need to have multiple states. In return, this is where animations pick up where transitions leave off.
- The keyframes rule is a must for animations. They must also include vendor prefixing.
- animatino name can be used to select the animation


*** Feature Support and polyfills ***
- Support for older browsers with polyfills, fallbacks etc.
- HTML shiv/shim provides html5 elements in older browsers
- For CSS feature detection you can use modernizr. THis way you can write conditional javascript and css for the browser.
- Selecting different files based on the browser can be done with conditioning. 
- polyfill is a way to get the same features in older browsers.
- 

*** Extending semantics and accessibility ***
- Semantics benefit everybody. 
    - structural semantics: Header, nav, article
    - text level semantics: bold, strong, 
- Microdata -> is HTML extended with nested groups of name-value pairs that allow machines, including browsers and search engines, to pick up additional semantics and information for rich content.
- Microdata vs Microformats vs RDFa -> they help google to better understand your website.
    - Microdata is support by google and takes both microformats and rdfa. 
    - google before making a choice on what to use.
- outlining microdata: itemscope, itemtype and itemprop

- WAI-aria: also know as Web Accessibility Initiative — Accessible Rich Internet Applications, is a specification that helps make web pages and applications more accessible to those with disabilities. 
    - Can be specified by roles 
        - document structure roles: define the organizational structure of content on a page. e.g. artcile, directory, heading
        - landmark roles: define the regions of a pages. e.g. applicaiton, form, banner
    

## own opinion
Great link: https://learn.shayhowe.com/advanced-html-css/performance-organization/ 
This is a very usefull site which I will probably refrence more. I converted the knowledge in there and added my own interpretation in this markdown file.
I love to see new features, but with the older browser support it is a bit of a let down. In the future I will try and add accessibility from the get go in my applications. 

