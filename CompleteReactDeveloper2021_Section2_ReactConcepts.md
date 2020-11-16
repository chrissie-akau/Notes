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
            - React had a whole new way to organize applications
