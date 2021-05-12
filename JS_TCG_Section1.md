What is JavaScript?
    - Dynamic weakly-typed programming language
    - Interpreted "on the fly" complied language
    - "Hosted language": Runs in different environments (or example in browser)
    - Most prominent use-case: Run code in a browser (on a webpage)

How is JavaScript Executed?
    - Your code goes into a JavaScript Engine which is built-into the browser (Chrome is V8, Firefox is SpiderMonkey etc.).  It parses code, complies t to machine code and executes the machine code (on a single thread) and you see the effects on the webpage.

Dynamic and Weakly Typed Language?
- Dynamic because...
    - Not pre-compiled instead parsed and complied "on the fly" 
    - Code evaluated adn executed at runtime
    - Code can change at runtime (ex. type of a variable)
- Weakly typed because...
    - Data types are assumed automatically 
    - You don't define that some variable has to hold a certain value (ex. number)
    - Data types are not set in stone, but can change.

JavaScript Runs On A Host Environment
Browser-Side Environment
- JavaScript was invented to create more dynamic websites by executing in the browser.
- JavaScript can manipulate the HTML code, CSS, send background HTTP requests and much more
- JavaScript can't access the local filesystem, interact with the operating system etc.
"Other" (ex. Server-side)
- Google's JavaScript Engine (V8) was extracted to run JavaScript anywhere called Node.js
- Node.js can be executed on any machine and can be used to build web backends (server-side JavaScript)
- Node.js CAN access the local filesystem, interact with the operating system.  It can't manipulate HTML or CSS

JavaScript and Java
- Totally independent programming languages with different syntax and principles
    - Java is object-oriented, strongly typed
    - JavaScript is flexible, weakly typed
    - JavaScript named after Java to sound cool (at the time)
    - Java doesn't run on the browser
- Client-Side Browser
    - Origin of JavaScript
    - Different browser vendors provide their own JavaScript execution engines
    - Allows interaction with web page and APIs
- Server-Side (NodeJS)
    - Allows for code and knowledge re-usage
    - Extracted V8 engine to run JavaScript anywhere
    - Special non-browser APIs
- Syntax, concept, core features are the exactly the same (client-side and server side)

A Brief History of JavaScript
- 1995 -> Netscaspe introduces "LiveScript"/"JavaScript"
- 1996 -> Microsoft releases its own version for Explorer.
- Late 1996 -> JavaScript submiited to ECMA (European Computer Manufacturers Association) to start standardization.
- 1997-2005 -> Standardization efforts, Microsoft didn't join and support standardization.
- 2006-2011 -> Microsoft finally on board, huge progress in ecosystem
    - Enormous progress in 2010 and 2011, became more unified. One core language we can use in different browsers.
- 2015-2016 -> brand new version of JavaScript (syntax etc.)
- ECMAScript -> JavaScript
    - ECMAScript evolved from the standards organization
    - JavaScript is the most famous ECMAScript implementation 
    - ECMAScript isn't directly used but browsers implement the standard into their JS engines
    - Each browser comes with its own JavaScript engine that also defines which features are actually supported.
    - Both are always under active development
