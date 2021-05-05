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