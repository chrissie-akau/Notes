React Basic Concepts
- Why React?  What problem does it solve?  What principles do we need to understand?

The Birth of React.js
- React was created in 2013
- What did we have before React?
    - 90s early 2000s -> Basic JS (interactivity), HTML (text), CSS (styling) in simple forms.
        - Problem: All these simple sites were run on different browsers with different developers.  As we wanted to use more JS, had to account for each of these browsers that worked differently from each other.
            - Jquery -> allowed developers to interact with DOM over all these browsers.  Had easy, unified syntax and API.  This allowed developers to make more complex applications as opposed to the more simple websites (we can log in, check status updates, etc.)
            - Backbone.js -> allowed us to organize all these files and we saw the birth of more libraries to assist in this. 
        - The Birth of Single Page Application (SPA)
            - Focus less on HTML and more on JS.  Instead of us making new requests to the server, instead we stay on the same page and the JS updates the HTML/CSS and DOM instead of calling on a server to update all of this.  This became very popular
            - Angular JS -> developed by Google in 2010.  Became the standard of building applications this way.  Allowed developers to build large applications wrapped in containers and because it was created by Google, it had a lot of power.  Everything was organized and had better containers.  
                - Created Model View Controller (MVC) or MVVM pattern -> each part of application was divided into the things that it did.  Making it easier to work with for large teams.  
                - Problem: Things started to get more and more complex and it was hard to find bugs in the code to see how each individual part was interacting with other parts.   Data was flowing everywhere.  
                - 2014 Angular rewrote their whole framework realizing their shortcomings after React was released.  During this time while they were re-writing Angular, people moved to React.  
        - Facebook Ads app was getting harder and harder to maintain because the amount of code and people working on it.  Each update was making it more and more complex and it was hard to keep up with (they were not using Angular.js).  They needed to upgrade their codebase.
        - The need for good architecture is very important.  How we organize our code, how we manipulate data and how that data flows through our programs.
        - Facebook's solution was React. 2013 it was released to the community.  
            - React had a whole new way to organize applications.  Great new principles it introduced, made it so popular.  What were these new principles it introduced?

Declarative vs. Imperative
First great key concept is:
1) Don't touch the DOM.  I'll do it.
    - Many existing frameworks were directly manipulating the DOM.  This is called Imperative Programming.
        - DOM -> Document Object Model - what the browser uses to display (website/web app).  JS manipulates the DOM.  The DOM is the tree representation of the page.  Libraries would provide an API to allow changes to the DOM.
        - Imperative Paradigm -> change individual parts of the app in response to user events.  Problem with this approach makes it hard to see the relationships between each of these events and edge cases (old Angular JS model) 
    - Declarative Paradigm -> React realized that DOM manipulation is a performance bottle neck.  
        - The DOM needs to do two major manipulations: 1) Repaint -> Change an element and add it on to a page 2) Reflow -> recalculate the layout of the page and move things around if need be.  React made this easier.  React says, what should the page look like?  I'll do it for you. Based on this state, make these changes.  This made got rid of us saying, "if this happens then do this, or if this happens do that."  We just tell it, this is the state of the app.  React automatically does it for us.  
        - All the different states are accounted for in one place; one big JS object.  Resulted in less complexity, better code quality, faster developer times.  It created a whole idea of building web interfaces without touching the DOM.  This is where the name React came from.

Component Architecture
Second great key concept is:
2) Build websites like lego blocks
    - React is designed around the idea of reusable components.  Small components put together to make them into larger components.  You have components containing other components.  All of these components can be used in different locations and projects.
        - Material UI/ ReactStrap -> all use the idea of reusable components.  You can just copy and paste these components and use them in a project.
    - Components -> are just JS functions that we write.  We have the State of our App.  Components are created based on this data simply as functions.  Components are functions that receive some sort of input or attributes which we call props, in return it returns JSX.  Can be built as function or a Class.  Based on the state and these components, we have an entire component for our page, like a NavBar or Profile Section.

