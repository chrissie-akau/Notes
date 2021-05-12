Full Stack Open Notes

Part 0
Fundamentals of Web Apps

    HTTP GET
        HTTP Protocol -> (Hypertext Transfer Protocol) is an application-layer protocol for transmitting hypermedia documents, such as HTML.  It was designed for communication between web browsers and web servers, but it can also be used for other purposes.  HTTP follows a classical client-server model, with a client opening a connection to make a request, then waiting until it receives a response.
            - Application Layer -> an abstraction layer that specifies the shared communications protocols and interface methods used by hosts in a communications network.
            - HTTP is a STATELESS Protocol -> the server does not keep any data (state) between two requests.

        GET Method -> HTTP GET requests a representation of the specified resource.  Requests using GET should only be used to request data (shouldn't include data)

        Status Code 200 -> OK - standard response for successful HTTP requests.

    Traditional Web Applications
        Traditional Web Application -> the browser fetches the HTML document detailing the structure and the textual content of the pages from the server. Document can be one of two things:
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
    