## What is Single page application (SPA)

A SPA is a web app that loads a single HTML page and dynamically updates only necessary content without reloading the page. It makes the user experience smooth and fast, similar to a desktop app.

## How SPA Works Internally?
Instead of fetching a new HTML page on every click, SPAs modify the DOM dynamically.

1. First-Load => When a user opens the SPA, the browser downloads:

- A single index.html file
- CSS and JS files
- A JS framework (like Angular/React/Vue)

2. Routing Without Page Refresh

- The app uses a Router (like Angular Router or React Router).
- When the user navigates, the URL changes but the page does not reload, router dynamically loads only the required components (like DashboardComponent ProfileComponent)

3. Fetching Data Asynchronously
- The frontend makes API requests (GET /api/dashboard)
- The backend responds with JSON data
- The frontend updates only the required UI elements

4. State Management (Optional)
- Instead of making frequent API calls, SPAs can store data in memory (Redux, NgRx, Context API)

5. Final Rendering & Interactions
- The app updates the DOM and shows new data instantly
- User interactions trigger events that update only specific sections of the page. (using V-DOM in react or change detection in angular)

## Need of SPA

-Faster load times(only required section get updated, not whole page), smooth navigation like desktop app, reduce server load(only json data is fetched saving bandwidth)

## Downsides

- SEO issue (solutions: SSR, prerendering)
- Initial load time.
- SPA rely on JS heavily making xss attacks possible.

**NOTE :** In SPA we have only one standalone/real HTML file i.e index.html, apart from that we have multiple components/templates. Browser dynamically loads other pages based on current route.

**NOTE :** In plain,traditional web-dev before SPA, each page of website was seperate HTML file (index.html, about.html,contact.html), when user click on html element/link browser would load entire new page making reqest to server(server side routing). SPA use client side routing
