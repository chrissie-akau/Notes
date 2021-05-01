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
