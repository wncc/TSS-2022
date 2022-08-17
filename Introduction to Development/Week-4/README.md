# Welcome to the Week 4 of Learner's Space React & NextJS!

We hope you got enough time to fully understand the foundational concepts of React JS and React Hooks.

This week's outline is as follows:

<ul>
<li> What is a Single Page Application?
<li> Routing in an Application
<li> React Router
<li> Protected Routes
<li> Introduction to Next JS
<li> Three Layered Web Architecture
</ul>

## What is a Single Page Application?

By now you must be aware of the fact that React JS is used to create smooth and fast Single Page Applications (SPAs).

In React the page contents are created from our components. When a request is being sent to the server, the contents are dynamically injected from the components we have created. This allows the content to be rendered faster without the page being refreshed.

Complicated enough?

In simple words, the idea of a single page application is to load all the HTML/JS the first time a website is visited. While navigating, the browser will only rerender the content without refreshing the website.

Basically, in a single page application a single HTML page and all the necessary JavaScript and CSS required to run the application is loaded while visiting the application for the first time. Any interactions with the page or subsequent pages do not require a round trip to the server, which means the page is not reloaded.

Let this sink in first, and then watch <a href = "https://www.youtube.com/watch?v=eIxDHgzGCnY&ab_channel=ProgrammingwithProfessorSluiter">this tutorial </a> if you're still unclear about what a single page application is.

## Routing in a React JS Application

If you'hv been doing the assignment along with this course, you might have developed an application by now which has multiple pages. Managing the routing and navigation in a large application becomes very messy if we don't have a smart way of routing through the application while preserving the state of the components.

In React, routers help create and navigate between the different URLs that make up your web application. They allow your user to move between the components of your app while preserving user state, and can provide unique URLs for these components to make them more shareable. With routers, you can improve your app’s user experience by simplifying site navigation.

## React JS Router

<a href = "https://reactrouter.com/">React Router</a> is one of the most popular routing frameworks for React. The library is designed with intuitive components to let you build a declarative routing system for your application. This means that you can declare exactly which of your components has a certain route. With declarative routing, you can create intuitive routes that are human-readable, making it easier to manage your application architecture.

At this point, I would like to emphasize again that learning React Router is extremely crucial if you want to build your own scalable React web applications.

Checkout <a href = "https://www.youtube.com/watch?v=59IXY5IDrBA&ab_channel=freeCodeCamp.org">this tutorial</a> and follow along to set up your router and build a small application!

## Protected Routes

Private Routes in React Router require a user being authorized to visit a route. So if a user is not authorized for a specific page, they cannot access it, in such cases they are usually redirected to some other page or home page.

If you understand how URLs work, you can try this fun activity in order to fully understand the concept of Protected or Private Routes.

If you or your friend has a netflix account, login into your/their account and select a movie that you wish to watch. Click on that movie and when the movie starts playing, copy the address of the webpage from the address bar. Now logout from your netflix account and just paste that link in the address bar and press enter, you'll notice that the movie doesn't play and you're redirected to some other route.

If you carefully notice, when you logged into your account you were authorized to visit and watch any movie through your netflix account. But all such routes are private or protected, that means a person with no netflix account cannot just directly visit the route and start playing the movie without even buying a subscription!

Making some routes protected or private is highly essential to avoid security breaches while designing a web application.

## Introduction to Next JS

In order to fully understand the advantages of Next JS over React JS, it is important to learn afew concepts first.

<ul>
<li> Client Side Rendering
<li> Server Side Rendering
<li> Search Engine Optimization
</ul>

### Client Side Rendering

Client-side rendering allows developers to make their websites entirely rendered in the browser with JavaScript. Instead of having a different HTML page per route, a client-side rendered website creates each route dynamically directly in the browser. This approach spread once JS frameworks made it easy to take.

### Server Side Rendering

Server-side rendering allows developers to pre-populate a web page with custom user data directly on the server. It is generally faster to make all the requests within a server than making extra browser-to-server round-trips for them. This is what developers used to do before client-side rendering.

### Difference between Client Side Rendering and Server Side Rendering

Client-side rendering manages the routing dynamically without refreshing the page every time a user requests a different route. But server-side rendering is able to display a fully populated page on the first load for any route of the website, whereas client-side rendering displays a blank page first.

Now if I have presented you all the concepts in a right manner and you have spent enough time reading them, you should be able to guess that React Applications are by default Client Side Rendered.

First I'll tell you the advantages of Client Side Rendered Applications:

### High Performance

CSR generates on-demand HTML. It will not refresh or re-render the whole page, as with regular HTML pages. It is just pretending to be a separate page, but it renders the content on a single page. This saves a lot of both computation power and RAM, so it gets quicker results than server-side rendering (SSR).

### Speed

CSR generates the HTML required to be displayed. This means DOM only contains enough code which is expected to be displayed by the HTML content. So DOM can easily handle a chunk of elements with the hide and show events. Although DOM has to handle more code, it doesn't take much time to render. Due to lazy loading, CSR becomes much faster than server-side rendering

Well! All of this seems perfectly fine to you right? What is the need of learning Next JS then? I just proved that React JS applications are fast and smooth because they are client side rendered. But there is one problem that client side applications cannot avoid with all their amazing features and that is the problem of <b>Search Engine Optimization.</b>

### Search Engine Optimization

Search engines such as Google and Bing use bots to crawl pages on the web, going from site to site, collecting information about those pages and putting them in an index. Think of the index like a giant library where a librarian can pull up a book (or a web page) to help you find exactly what you’re looking for at the time.

Next, algorithms analyze pages in the index, taking into account hundreds of ranking factors or signals, to determine the order pages should appear in the search results for a given query. In our library analogy, the librarian has read every single book in the library and can tell you exactly which one will have the answers to your questions.

Our SEO success factors can be considered proxies for aspects of the user experience. It’s how search bots estimate exactly how well a website or web page can give the searcher what they’re searching for.

<b>Client Side Rendering requires a two-wave process for JS rendering and indexing in a browser, generally by Google.

The first wave requests the source code, crawls, and then indexes the presented HTML. But in CSR we don't have much of the HTML because it takes time to convert from JavaScript to HTML.

In the second wave, after all resources become available, the browser returns the additional support and index to the search engine. This is not a problem with server-side rendering because in server-side rendering, the HTML is available for the first time itself.</b>

I hope you understood that React JS applications by default are not search engine optimized and that is precisely why we need to learn Next JS. Next JS has some other cool features as well, such as easy routing!

It's time to watch a video tutorial now, please head over to this final link in order to start learning Next JS.

<a href = "https://www.youtube.com/watch?v=F1JSkWma3_8&ab_channel=codedamn"> Why to Learn NEXT JS? </a>

<a href = "https://www.youtube.com/playlist?list=PL4cUxeGkcC9g9gP2onazU5-2M-AzA8eBw">Playlist to Learn NEXT JS</a>

## Three Layered Architecture [OPTIONAL]

Note: As a software developer, a person should be clear with the concepts of Three Layered Architecture as it helps in smooth and faster development.

A three-tier architecture is a client-server architecture in which the functional process logic, data access, computer data storage and user interface are developed and maintained as independent modules on separate platforms.

Three-tier architecture is a software design pattern and a well-established software architecture.

The three tiers of Three Layered Architecture are:

### Presentation Tire

Occupies the top level and displays information related to services commonly available on a web browser or web-based application in the form of a graphical user interface (GUI).

It constitutes the front-end layer of the application and the interface with which end-users will interact directly.

This tier is usually built on web development frameworks, such as CSS or JavaScript, and communicates with other tiers by sending results to the browser and other tiers in the network through API calls.

### Application Tire

This tier — also called the middle tier, logic tier, business logic or logic tier — is pulled from the presentation tier.

It controls the application’s core functionality by performing detailed processing and is usually coded in programming languages, such as Python, Java, C++, .NET, etc.

### Data Tire

Houses database servers where information is stored and retrieved.

Data in this tier is kept independent of application servers or business logic, and is managed and accessed with programs, such as MongoDB, Oracle, MySQL, and Microsoft SQL Server.

## Assignment 

Now comes the assignment that you all have been waiting for. NextJS is not difficult if you are comfortable with ReactJS. 
For this week's assignment there not much as compared to other weeks' assignment. It'd be pretty easy if you are good with react and have a smooth transition to the NextJS's SSA(Server-side rendering).
<br><br>
You have to make your existing website(the inventory website) a progressive-web-app (PWA) and also transition it to server side rendering for SEO.

