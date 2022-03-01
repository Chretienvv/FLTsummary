# Subject
Angular introduction big picture, architecture etc.

## Tips 
***Benefits***
- Standards compliance
    - internationalization, accessibility, modules, es6
- Reduction of cost because of reusable code
- Open source & popularity & Documentation & google backing
- Performance
- Libraries like
    - Router, http, forms, rxjs etc.

***features***
- PWA's, Lazy Loading, Forms, RXJS, Router,
- Server side rendering, Mobile, angular language service, ngupgrade (mutliple versions)

***Architecture***
- One way data flow (change detection)
- Dependency Injection -> 
`export class AddNewTagComponent {constructor(private articleSvc: ArticleService){}}`
- Component based
- Templates -> how the components are built -> seperate from the component.
- Directives -> add new capabilitys to an element. hover-trigger
- State changes order
    - State change -> first name
    - Cascading changes -> full name
    - re-render -> display of full name
- Rendering options
    - Browser platform (dynamic)
    - DOM, server-side, native mobile, native desktop 
- Server side rendering benefits performance for
    - initial download size
    - render time
    - SEO
- Server side rendering operation modes
    - Full pre render
    - Dynamic pre render
    - Client side switch ( download app, boots the app and replays any events)
- AOT process (ahead of time)
    - compiler is at the server, it sends the code and framework to the browser.

*** Tips, tricks, gotchas ***
- Gotchas
    - Decorators are a new type of syntax
    - Custom Pipes 
        - Pure and impure
            - Pure: oinly evaluated when input changes
            - Impure evaluated on every change detection cycle.
    - Module API is complex and does a lot.
    - Multiple modules difficulties
        - Routing, importing and exporting
    - RxJS complexity 
        - Observables, Hot-cold- shared observables, self subscribe or not, forgetting to subscribe, multiple http requests
    - Cryptic error messages
- Tips/ Tricks
    - Sorting and filtering in your component
    - Follow the sytle guide,  Ngrx, Webpack, Lazy loading
    - Don't touch the DOM directly
    - Understand what you send

## own opinion
I have used angular in the past and it is awesome. Although it has some downsides for small projects it is for most enterprises interesting. I like the way of building components and services to create an application with a niice overview.