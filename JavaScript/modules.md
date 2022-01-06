# Modules
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules 
## Tips 
- What are modules
    - Import and export
    - Encapsulated code
    - Control acces
    - Reference its own dependencies
- Module considerations
    - Modules are singletons
        - Singletons: Any other modules can import your module but they will use the same instance of it.
    - Poperties are bound. ( exported and changed it changes everywhere)
    - Exports are static at runtime
    - One module per file. 
        - One file per http request, HTTP/2 will be fine with sockets
            - Module bundle like webpack solves this problem

- Named exports
    - export named functions, classes, variables etc.
    - import it on the file where you need it with the appropiate names.
    - You can also bundle it with export {}
    - Export XX as YY you can rename it for the import
    - Struggle is that you have to know what the name is.
- Default exports
    - Default keyword. 
    - import YouCanChooseAName from the file.

- Aggregating modules
    - putting multiple modules in module
    - This way you dont need to import 500 different files

- Enabling modules
    - in the html script tag use type="module" 
- Default imports
    - Mostly has to do with export default. 
- Named imports
    - Need to import the same name and use the {} aroung the name. Now you can do multiple like {1, 2}
    - You can till change the name with as
- Import * as Template . to use all the exports with template.blabla

## own opinion
Very usefull for the abstraction level of code.  The aggregating of modules is a bit weird for now. I know why it is helpfull but I dont think it helps with the transparency of the imports.
Knowing what you import is very important. The same with usage of libraries. 