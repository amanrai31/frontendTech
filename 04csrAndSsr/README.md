## SSR AND CSR (Server side rendering & client side rendering)

## CSR

CSR means the browser (client) loads a blank HTML page and builds everything using JS.

**How CSR Works?**
1. User requests a page → example.com/home
2. Server sends a blank HTML file with a <script> tag for JS.
3. The browser downloads JS files and executes them.
4. JS fetches data from APIs and dynamically builds the page.
5. The page becomes interactive only after JS execution.

**Issue with CSR -** HTML generated in browser so user sees a blank page until JS loads (slow 1st load), search engines don't see any content because of empty HTML leads to bad *SEO*. Also low-end device struggle to process heavy JS.

## SSR

SSR means the server generates a complete HTML page with content and sends it to the browser.

**How SSR Works?**
1. User requests example.com/home.
2. Server runs JS on the backend **(SSR Function)**, fetches data from APIs, and generates a full HTML page and send pre-rendered HTML to browser.
3. The browser immediately displays the page.
4. JS then "hydrates" the page (makes it interactive).

**Why SSR -** HTML generated on server before sending to browser i.e. fast 1st load (no blank page), better SEO(Search engine can read & index the page)

## Key difference

In CSR we see skeleton UI immediately(partial rendering), HTML generated on browser, data fetching happens after page-load.
In SSR initial load is blank until the server responds, HTML page generated on server and data fetching done before sending HTML to browser.


### Modern framework for SSR
NextJs (react) => Hybrid SSR & CSR
Angular universal => SSR for Angular


-----------------------------------------------------------

### Downside of SSR

1. Slower response times – If API calls are slow, users will have to wait.
2. Higher server load – Every request triggers a new render.

#### Solution (Best practices)

1. Use caching (redis(memory caching) or nextJS built-in caching(Incremental static regeneration))
2. use hybrid rendering i.e. use SSR only when there is fetching of data involved(for user-specific content), use CSR for pages that don't change often.
3. Optimize API call in SSR using parallel API fetching (promise.all)

```tsx
export async function getServerSideProps() {
  const [usersRes, postsRes] = await Promise.all([
    fetch("https://api.example.com/users"),
    fetch("https://api.example.com/posts"),
  ]);

  const [users, posts] = await Promise.all([usersRes.json(), postsRes.json()]);

  return { props: { users, posts } };
}

```

## Hydration

Once the server sends the pre-rendered HTML, the browser loads React(attach event listeners) and makes the page interactive. This process is called hydration.

**NOTE :** If page has lot of interactivity, hydration is slow and competes with other task making page laggy. We can use lazy hydration or can use Streaming SSR (<suspense fallback={Loading/}><Post/></Suspense>).

## JSX and SSR

1. JSX is compiled to JavaScript (React.createElement)
2. React converts JSX to pure HTML (renderToString()) (on server)
3. The server sends HTML to the browser
4. React hydrates the page, making it interactive