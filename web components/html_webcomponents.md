# Web components

## Tips
- Currently 5 problems in web development. Undescriptive markup, style conflicts, no native templats, no bundling, no standard.
- Web components will make markup easier to describe and read.
- Template child nodes are not accessible by JavaScript or CSS with .getElementBY.... but it needs to be template.content

- What are webcomponents?
  - A container name for custom elements, shadow dom and html templates.
  - No framewoasdfrk or runtime. Directly on the browser standards.
- Custom element
  - Needs to desend from the HTMLElement class
  - Name must be XXX-XXX
- Shadow DOM

  - Creation of a new shadow tree

            <div class="shadow"></div>

            <script>
            // Attach new shadow root to the div element
            const node = document.querySelector('.shadow');
            node.attachShadow({ mode: 'open' });

            // Use node.shadowRoot to manipulate the shadow DOM
            node.shadowRoot.innerHTML = '<p>Hello...</p>';

            // You can also use node.shadowRoot.querySelector
            // and anything you usually use to manipulate DOM

            // Append a new <span> element to the shadow DOM of
            // the node element
            const message = document.createElement('span');
            message.textContent = '...world!';
            node.shadowRoot.appendChild(message);
            </script>

    - Open -> possible to interact with queryselector with nodes inside the shadow dom.
    - Closed -> no interaction possible

- Power of Template
    - Already parsed so with clonenode it is super fast.
- Slot element can be used within templates to specify the place for html outside the template.




***custom elements ***
- Define your own html elements with a dash
- Registering the custom element can be done with property on native elements as well. 
- Can extend prototypes or other custom elements.
- Different instantiate options
    - Declare in markup with the attribuet is
    - JavaScript with document. create Element
    - new operator new Car()
- Lifecycle callback methods
    - createdCallback, attachecCallback, detachedCallback, attributeChangedCallback

***Shadow Dom***
- Light DOM -> dev tools elements. 
- Shadow DOM -> hides away complexity. 
- Shadow Host -> Element in the light dom that is hosting the shadow dom.
- Shadow Boundary -> A concept to describe the boundary between the light and shadow dom. It protects the shadow DOM subtrees.
- Insertion Points with the content tag. This ***displays*** a html tag into the shadow DOM. 
    - The first content tag that matches wins.
- distributed nodes are the elements inside the insertion points. These elements are not inserted, they are displayed.
- Shadow insertion points -> Shadow tag.  Multiple shadow trees inside eachoter. Again the shadow tags have the concept of the first one wins.
- Listing distributed nodes
    - getDestinationInsertionPoints
    - getDistributionNodes
- JavaScript is not encapsulated in the shadow dom
- JavaScript event retargeting -> An event on a shadow element refers to the shadow host.
- Events that stop in the shadow DOM - abort, error, select, change, load, reset, resize, scroll, selectstart.


***Shadow DOM styling***
- CSS selectors - :host, shadow, deep, unresolved, content, host-context.
- host pseudo selector -> styles the shadow host. Can be overriden by more specific selectors.
    - Can still benefit from states such as hover, active linked etc.
    - :host-context -> pierces the shadow boundary to find the right context for styling. 
- Styling distributed nodes can be done with ::content
- Styling Shadow Dom from the light DOM with ::shadow. 
    - Tweak the style of a web component via the shadowroot. 
- /deep/ styles all shadow dom elements. pierces all boundaries and all shadow trees.
- :unresolved fallback when the original call is not resolved. It only applies to custom elements.


***Imports***
- Templates versus imports. 
- Imports support storing eert html in a seperate file and bundling.
    -  link rel="import" href
- inmports are usefull for themes, component libraries and app sections
- link element has two events. onload and onerror Describe them above the link tag.
- Eliminate duplicate and conflicting resources.

## own opinion



## Sources

https://www.arcady.nl/updates/web-components-101-part-1/ Also includes libraries, code, tooling, scaling and the next level

Open web components https://open-wc.org/guides/developing-components/getting-started/

Modern web: https://modern-web.dev/guides/
Ing web components library
