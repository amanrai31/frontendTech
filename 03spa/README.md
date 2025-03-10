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
- When the user navigates, the URL changes but the page does not reload, router dynamically loads the required components (like DashboardComponent ProfileComponent)