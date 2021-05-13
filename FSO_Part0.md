Fundamentals of Web Apps

HTTP GET
- HTTP Protocol -> (Hypertext Transfer Protocol) is an application-layer protocol for transmitting hypermedia documents, such as HTML.  It was designed for communication between web browsers and web servers, but it can also be used for other purposes.  HTTP follows a classical client-server model, with a client opening a connection to make a request, then waiting until it receives a response.
    - Application Layer -> an abstraction layer that specifies the shared communications protocols and interface methods used by hosts in a communications network.
    - HTTP is a STATELESS Protocol -> the server does not keep any data (state) between two requests.

        GET Method -> HTTP GET requests a representation of the specified resource.  Requests using GET should only be used to request data (shouldn't include data)

        Status Code 200 -> OK - standard response for successful HTTP requests.

Traditional Web Applications
- Traditional Web Application -> the browser fetches the HTML document detailing the structure and the textual content of the pages from the server. Document can be one of two things:
    - Static-> Text File saved into the server's directory
    - Dynamic -> form the HTML documents according to the application code using, for example, data from a database.  Example app is dynamic because it contains information on the number of created notes.
        - The browser is dumb -> only fetches HTML data from the server, and all application Logic is on the server.  

        Server -> essentially what is running the back end.  It can be created using Ruby on Rails, Java Spring, Python Flask, Node.js, and Express. 
        
        HTML Code for homepage:
            const getFrontPageHtml = (noteCount) => {
            return(`
                <!DOCTYPE html>
                <html>
                <head>
                </head>
                <body>
                    <div class='container'>
                    <h1>Full stack example app</h1>
                    <p>number of notes created ${noteCount}</p>
                    <a href='/notes'>notes</a>
                    <img src='kuva.png' width='200' />
                    </div>
                </body>
                </html>
            `)
            } 

            app.get('/', (req, res) => {
            const page = getFrontPageHtml(notes.length)
            res.send(page)
            })
        
         - This has been saved as a template string, or a string which allows for evaluating, for example, variables in the midst of it.  This example, not the best example of code with HTML right in the middle (PHP Programmers had to do this), but the dynamically changing part of the homepages is the number of saved notes which is noteCount and it is replaced by the current number of notes, notes.length in the template string.

Running Application Logic On The Browser
- JSON -> (JavaScript Object Notation) "raw data" is an open standard file format and data interchange format that uses human-readable text to store and transmit data objects consisting of attribute-value pairs and arrays.  It is a very common data format with a diverse range of applications.  

    JavaScript code of the notes page above downloads the JSON-data containing the notes, and forms a bullet-point list the note contents by the following code:
        const data = JSON.parse(this.responseText)
            console.log(data)

            var ul = document.createElement('ul')
            ul.setAttribute('class', 'notes')

            data.forEach(function(note) {
            var li = document.createElement('li')

            ul.appendChild(li)
            li.appendChild(document.createTextNode(note.content))
            })

            document.getElementById('notes').appendChild(ul)
        
        Code first creates an unordered list with a ul-tag and adds one li tag for each note.  Only the content field of each note becomes the contents of li-tag.  The timestamps found in the raw data are not used for anything here.

Event Handlers and Callback Functions
    xhttp.onreadystatechange = function () {
        if(this.readyState == 4 && this.status == 200) {
        }
    }
-  When the state of the object changes, the browser calls the event handler function.  The function checks that the readyState equals 4 and the HTTP status code of the response is 200.
-  Event handler functions are called callback functions.  The code doesn't invoke the functions itself, but the runtime environment - the browser, invokes the function at an appropriate time, when the event has occurred.

Document Object Model or DOM
- HTML elements look like a tree:
    <html>
        <body>
            <div class="container">
                <h1>Notes</h1>
            </div>
            <div id="notes">
                <ul class="notes">
                    <li>HTML is easy </li>
                    <li>Browser can execute only JavaScript</li>
                    <li>Most important methods of HTTP-protocol are GET and Post</li>
                </ul>
            </div>
        </body>
    </html>
- The Document Object Model or DOM is an Application Programming Interface (API), which enables programmatic modification of the element trees corresponding to web-pages.  
- JavaScript code creates a new node to the variable ul and adds some child nodes to it:
    var ul = document.createElement('ul')
    data.forEach(function(note){
        var li = document.createElement('li')
        ul.appendChild(li)
        li.appendChild(document.createTextNode(node.content))
    })
    - The tree branch of the ul variable is connected to its proper place in the HTML tree of the whole page:
        document.getElementById('notes').appendChild(ul)

CSS
- Cascading Style Sheet (CSS) is a markup language used to determine the appearance of web pages.
    - Can manipulate from the Element in the Console.

Forms and HTTP Post
- Sends data to the server and results in a change on th server.
    - Difference between PUT and POST
        - PUT is idempotent, calling it once or several times successively has the same effect (no side effect), where successive identical POST requests may have additional effects, like passing an order several times.
- HTTP Status Code 302 is a URL redirect -> where the server asks the browser to do a new HTTP GET request to the address defined in the header's Location, in this case, the address notes.  The browser reloads the Notes page and causes three more HTTP requests: fetching the style sheet, the JavaScript code, and the raw data of the notes (the json).

AJAX
- AJAX (Asynchronous JavaScript and XML) enabled the fetching of content to web pages using JavaScript included within the HTML, without the need to rerender the page.

Single Page App
- Single-page Application (SPA) -> do not fetch all of their pages separately from the server, but instead have one HTML page fetched from the server, and the contents are manipulated with JavaScript that executes in the browser.

JavaScript Libraries
- JavaScript libraries -> contain tools that are easier to work with compared to the DOM-API and using vanilla JavaScript.
- Library Examples:
    - jquery -> developed back when web applications were more traditional, generating several HTML pages instead of SPAs.  It had cross-browser compatibility. 
    - Angular, React, VueJS -> more modern ways of web development following the SAP way.

Exercises
- HTML -> a markup language that defines the structure of your content. It consists of a series of elements that you enclose or wrap to make it appear or act a certain way.
- CSS -> cascading style sheet.  Made up of a ruleset:
    ex.
    p {
        color: red;
    }
    - Selector -> p in this case, defines the element to be styled.
    - Declaration -> color: red in this case, specifies which of the element's properties you want to style.
    - Properties -> color in this case, which property you want to affect in the rule.
    - Property Value -> red in this example, anything to the right of the property.