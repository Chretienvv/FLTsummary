# Javascript security best practices
Unique javascript security issues
## Tips 

- Basic notions of Web security
    - Attackers: Capable and motivated
    - Vulnerabilities: Flaws in code and configuration
    - Data breaches: Steal data or abuse functionality

- Javascript security pitfalls
    - Dynamic type system: Abusing conversions and comparisons
    - Dynamic code execution: interpreting untrusted data as code
    - Prototypal inheritance: Modifying behaviour of child objects

- Browsers execute javascript code in the following way:
    - Code is downloaded
    - Each site gets a sandbox where the javascript code is executed.
    - Multiple security measures
        - HTTPS
        - OS process separation
        - Subresource integrity (SRI)

- Browser sandbox
    - NO local resources: No direct acces to devices, files and local network
    - Only browser apis: limited acces to resources allowed by the user
    - Same origin only: code and data from different sites cannot interact

- Javascript in the browser vs Javascript in node.js
    - Downloaded from the web - loaded from local files
    - untrusted and highly restricted - Trused and highly privileged
    - Limited blast radius - May lead to server compromise

- Dynamic type system pitfalls ( loos comparison vulnerability)
    - Automatic conversions: Unexpected code may be executed
    - Stric ===
    - Loose comparision ==
    - Always use strice mode

- How to exploit this bug? ^ 
    - Modify datat to confuse the type system
        - Mixed data types
        - Arrays and objects
        - Missing properties
    - Inspect original http request
    - Inject malicious payload using browser development tools
    - Deliver it to the application

- Object.is can also be usefull, use === instead
- Verfiy types of untrusted data items


*** Code injection vurnerabillities ***
- Dynamic code execution
    - Javasscript code can be loaded from web, files or user input
    - Parse: Transform source code into abstract syntax tree
    - Compile: Generate bytecode just in time
    - Execute: Run bytecode instructions
        - Bytecode is program code that has been compiled from source code into low-level code designed for a software interpreter. It may be executed by a virtual machine (such as a JVM) or further compiled into machine code, which is recognized by the processor.
- Javascript can generate and execute new code at runtime.
- Arithmetic expression
    - https://www.w3schools.com/js/js_arithmetic.asp 
    - Performs e.g let test = math.eval('(1+1) * 2)

- Unsafe functions
    - Usefull website: https://docs.qualityclouds.com/qcd/javascript-avoid-use-of-function-constructors-31719691.html 
    - Eval 
        - Eval(code)
        - Direct and indirect invocation
        - glpbal and current scope
    - Function constructor
        - f = new function(param, code) f('argument')
        - Invoke like a function
        - only global scope
        - Non compliant: var obj = new Function("return " + data)(); // Noncompliant
        - Compliant: var obj = JSON.parse(data);

- Unsafe browser api
    - Not safe because the use of global variables
    - setTimeout: execute provided code after a specified delay
    - setInterval: repeateldy execute provided code with a specified delay between executions
```
// safe
setTimeout(function() {
    doSomething(someVar);
}, 10000);

//unsafe
setTimeout('doSomething(someVar)', 10000);
```

- Impact of code injection attacks
    - Denial of service
    - Modify application logic
        - Bypass acces control
        - Compromise data integrity
        - Steal sensitive data
    - Server takeover
- Web shell
    - Definition: A web shell is a type of web server malware. It is a script uploaded to your web server by an attacker and executed there. The term shell is used to describe a user interface that you use to access services offered by the operating system
- Fixing code by:
    - Avoid unsafe functions
    - Validate input
        - Prefer allow lists over block lists
        - Sanitize data passed to interpreters
        - Apply principle of east authority

- Third party code
    - Third party pacakages may be prone to code injection
    - validate input data before passing them to libraries
    - External packages need to be audited for use of unsafe functions



*** Defending against prototype pollution ***
- Prototype pollution: Modifying the prototype chain in a way the code cant handle it.
- Polluting the object prototype
    - Denial of service
    - For in loo manipulation
    - Property injection
        - Security check bypass
        - SQL an NoSQL injections
    - Remote code execution

```
// Prototype pollution example
const user = {name: ' full name'}; // regular user
const malicious = {isAdmin: true}; // isadmin is true for administrators only
user['__proto__'] = malicious // Polution
console.log(user.isAdmin) // true. escalation of privilege

```
- Prototype pollution code smells
    - Property mutation with untrusted key and value
    - Recursive object merging
    - object cloning: When deep copying objects.
    - Property acces by path
- Protecting the prototype
    - Validate JSON schema
    - Freeze the prototype
    - Create objects without prototype
        - Object.creat(null, ...)
    - Use Map instead of { }

- Pollution through third party libraries
    - Utility libraries
    - Merging, cloning, extending.
    - Not using Third party libraries is not practical.
    - Examples of libraries that are used a lot but had security vurnelabilities
        - JQuery
        - Lodash
        - Hapi


*** Testing your code ***
- Security testing techniques
    - SAST: Static application security testing
    - DAST: DYnamic application security testing
    - IAST: Interactive application security testing

- SAST vs DAST
    - Source code vs Running application
    - Known bad code patterns vs Malicious payloads
    - Safe vs May be destructive because they send payloads. Do not run in production
    - Compoilers, linters, scanners vs automated tests and scanners

- Example linting tool ESLINT
    - Parse code and analyze the abstract syntax tree (AST)
    - Extensible: Comes with a set of bundled checks
    - Fast: Can be used by ides and build pipelines

- Using unit tests to detect prototype pollution
    - Pro's
        - Reliable and repeatable
        - Easy payload delivery
        - Inspect program state after attack
            - Input violating assumptions about types
            - Code injection effects
            - Detect prototype pollution
    
- Popular testing tools
    - SAST
        - ESLINT
        - Github code scanning
        - LGTM
        - semgrep
    - DAST
        - OWASP ZAP
            - Many ccommercial alternatives
    - Dependency management
        - NPM audit
        - retire.js
        - Dependency-Track
        - Snyk
    
## own opinion
This really opened my eyes to the security of code. Some practices were already in may way of working but certainly not all. 
I think it is very interesting and a really extensive subject that can make or break a system. 
This should be a top priority when developing. 