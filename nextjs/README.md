# Next-js-Questions-and-Answers
### 1. What is Next Js?
Next.js is an open-source, lightweight React.js framework that gives you building blocks to create web applications. Next.js was first released as an open-source project on GitHub on October 25, 2016. It was created by Zeit. By this framework, mean Next.js handles the tooling and configuration needed for React, and provides additional structure, features, and optimizations for your web application.

### 2. How to install Next js?
Developers will need NPM to start installing Next JS with all its dependencies. Here are the steps to follow:

Create a directory to keep the Next JS project and go into it:

- mkdir my-portfolio-site
- cd my-portfolio-site

- Now initialize this with a package.json file.

- Use the y flag by npm init –y
- Use the below-mentioned syntax to install Next JS
- npm install react react-dom next
- Update package.json with run script languages to start the initialization of Next JS application.
   
Please find the package.json file on root folder and add the below mentioned script
```json
"dev": "next",
"build": "next build",
"start": "next start"
```
Now, we are finished with the process.

### 3. What are the features of next js?

For React developers, NextJS has a lot of advantages. Let's go over all of NextJS's features :
 
- **Automatic Routing :** There's no need to set up URLs for routing. The files should be saved in the pages folder. The file system will be mapped to all URLs. Customization is possible.

- **Dynamic Components :** Next.js allows us to import JavaScript modules and React Components.
 
- **Component-specific styles :** Global and component-specific styles are supported by styled-jsx.
 
- **Server-side rendering :** As React components are prerendered on the server, they load more quickly on the client.
 
- **Node Ecosystem :** As Next.js is React-based, it fits well with the Node ecosystem.
 
- **Automatic code split :** Next.js renders pages with all of the required libraries. Next.js creates multiple resources rather than a single large javascript file. Only the required javascript pages are loaded when a page is loaded.
 
- **Prefetch :** Next.js is a framework for developing web applications. The prefetch property of the Link component, which is used to link multiple components, can be used to prefetch page resources in the background.
 
- **Export Static Site :** With Next.js, we can export our entire static site from our web application.

- **Hot Code Reload :** The Next.js server detects modified files and automatically reloads them.
 
- **Built-in Typescript Support :** Next.js is a Typescript-based framework with excellent Typescript support.


### 4. What is AMP in Next JS?
This is a Next JS standard used to build high-performance websites rendering overhead. AMP implemented websites are indexed faster in modern and popular search engines with enhanced promoting behavior. AMP web pages are loaded directly to Google's mobile search results with a lightning icon, better performance, fewer restrictions, and better scalability.

### 5. How to validate AMP in the next JS?
To validate your AMP pages, ‘amphtml-validator’ is used during the development. Warnings and fatal errors will be displayed in the terminal where the Next JS is started. AMP pages also get validated during ‘next export’ and issues will be printed in the terminal, and the ‘next export’ will fail due to the absence of proper AMP validation.

### 6. How to enable AMP in Next JS?

This one is crucial. Next JS interview question to practice and remember all its aspects. There are two processes to enable AMP in Next JS. The thing to remember here is, AMP is a crucial part of many Next JS interview questions, so we would advise it to practice well.

    AMP-First Pages

These are served to the primary traffic of the website as well as traffic generated from the search engine. We have to use the following syntax to implement AMP-first pages.

    Hybrid AMP Pages

Hybrid AMP pages allow users to have a coexist AMP version of a traditional page so that search engines can easily display the AMP version or the page in different mobile search results. To implement Hybrid AMP to pages, we have to use the following syntax.

```javascript


AMP-First Pages :-

// pages/index.js

import { withAmp } from 'next/amp'

function HomePage() {

return <p> Welcome to AMP + Next.js.</p>

}

export default withAmp(HomePage)

 
 
Hybrid AMP Pages :-

// pages/index.js

function HomePage() {

return <p> Welcome to AMP + Next.js.</p>

}

export default withAmp(HomePage, { hybrid: true })

```

### 7.What are the benefits of implementing Serverless mode and how to implement it? 
Implementing Serverless mode excellently improves scalability and readability of an application by splitting it into smaller parts known as lambdas. It also promotes affordability with a "pay for what you use" model.

To enable Serverless mode in Next JS, we have to add ‘serverless’ build target in next.config.js.
#### Example
```javascript

// next.config.js

module.exports = {

target: 'serverless'

}

```
### 8. Does Next JS support static CDN?
Yes, Next JS 5 and above supports static CDN. With the introduction of assetPrefix, Next.JS automatically loads assets from CDN.

### 9.Why is Next.js used for? and Why do world's leading companies prefer Next.js?

If you want to build a complete web application with React from scratch, you have to fulfill the following points :
 
- Your code has to be bundled using a bundler like webpack and transformed using a compiler like Babel.
- You have to do production optimizations such as code splitting.
- You have to pre-render some pages for performance and SEO statically. You might also want to use server-side rendering or client-side rendering.
- You might have to write some server-side code to connect your React app to your data store.

Next.js fulfills the above all requirements.
 
Reasons why the world's leading companies prefer Next.js :

- **Zero Setup :** Next.js provides automatic code-splitting, filesystem-based routing, hot code reloading, and universal rendering; that's why the world's leading companies prefer it.
 
- **Fully Extensible :** Next.js is fully extensible and has complete control over Babel and Webpack. It provides a customizable server, routing, and next plugins.
 
- **Ready for Production :** Next.js is optimized for smaller build sizes, faster dev compilation, and many other improvements, making it a popular choice.
 
- **Next.js can Deploy Anywhere :** Next.js is an open-source, lightweight React.js framework that facilitates developers to build static and server-side rendering web applications.

### 10. What is Building Blocks of a Web Application in Next.js?

There are a few things you need to consider when building modern applications. Such as:
 
- **User Interface -** how users will consume and interact with your application.

- **Routing -** how users navigate between different parts of your application.

- **Data Fetching -** where your data lives and how to get it.

- **Rendering -** when and where you render static or dynamic content.

- **Integrations -** what third-party services you use (CMS, auth, payments, etc) and how you connect to them.

- **Infrastructure -** where you deploy, store, and run your application code (Serverless, CDN, Edge, etc).

- **Performance -** how to optimize your application for end-users.

- **Scalability -** how your application adapts as your team, data, and traffic grow.

- **Developer Experience -** your team’s experience building and maintaining your application.

For each part of your application, you will need to decide whether you will build a solution yourself or use other tools such as libraries and frameworks.


### 11. Which types of websites most popularly use Next.js?

Next.js is a popular framework of React.js that is most popularly used for building the following types of apps and websites :
 
* Static Websites
* Desktop Websites
* SEO Friendly Websites
* Server Rendered Apps
* Progressive Web Apps (PWA) etc.


### 12. What is the recommended method to fetch data in Next.js?

There are multiple ways to fetch data in Next.js, but Next.js itself recommends **getInitialProps, an async function** to retrieve data from anywhere. When we use getInitialProps to retrieve data, it receives a context object which has the following properties :
 
* pathname : It specifies the path section of the URL.

* query : It is used to specify the query string section of URL parsed as an object.

* asPath : It specifies the string of the actual path (including the query) shows in the browser.

* req : It is used to specify the HTTP request object (server only).

* res : It is used to specify the HTTP response object (server only).

* err : It is used to specify the error object if any error is encountered during the rendering.


### 13. How can you disable the etag generation in Next.js?
Generally, we use the app.disable('etag') syntax to disable the etag generation in Next.js. But, this may not work for all static contents. So, we should use the following syntax to disable the etag for all static contents.
 
**Syntax :**
```javascript
app.use(express.static(path.join(__dirname, 'public'), {  
etag: false  
})); ​
```


### 14. How can you configure the build-id in Next.js?
To configure the build-id in Next.js, we must configure a static ID between our builds. So, we have to provide the "generateBuildId" function with the following configuration.
 **Syntax :**
```javascript
// next.config.js  
module.exports = {  
   generateBuildId: async () => {  
  // For example get the latest git commit hash here  
  return 'my-build-id';  
  }  
};​
```
### 15. Why use Create Next App?

create-next-app allows you to create a new Next.js app within seconds. It is officially maintained by the creators of Next.js, and includes a number of benefits :
 
* **Interactive Experience :** Running npx create-next-app@latest (with no arguments) launches an interactive experience that guides you through setting up a project.
 
* **Zero Dependencies :** Initializing a project is as quick as one second. Create Next App has zero dependencies.
 
* **Offline Support :** Create Next App will automatically detect if you're offline and bootstrap your project using your local package cache.
 
* **Support for Examples :** Create Next App can bootstrap your application using an example from the Next.js examples collection (e.g. npx create-next-app --example api-routes).
 
* **Tested :** The package is part of the Next.js monorepo and tested using the same integration test suite as Next.js itself, ensuring it works as expected with every release.

### 16. What is Data Fetching in Next.js?
Data fetching in Next.js allows you to render your content in different ways, depending on your application's use case. These include **pre-rendering with Server-side Rendering or Static Generation**, and updating or creating content at runtime with **Incremental Static Regeneration**. 

### 17. What is Client-side data fetching in Next.js?

**Client-side** data fetching is useful when your page doesn't require SEO indexing, when you don't need to pre-render your data, or when the content of your pages needs to update frequently. Unlike the server-side rendering APIs, you can use client-side data fetching at the component level.
 
If done at the page level, the data is fetched at runtime, and the content of the page is updated as the data changes. When used at the component level, the data is fetched at the time of the component mount, and the content of the component is updated as the data changes.
 
It's important to note that using **client-side** data fetching can affect the performance of your application and the load speed of your pages. This is because the data fetching is done at the time of the component or pages mount, and the data is not cached.

### 18. What is Client-side data fetching with SWR in Next.js?
The team behind Next.js has created a React hook library for data fetching called SWR (stale-while-revalidate). It is highly recommended if you are fetching data on the client-side. It handles caching, revalidation, focus tracking, refetching on intervals, and more.
 
Using the same example as above, we can now use SWR to fetch the profile data. SWR will automatically cache the data for us and will revalidate the data if it becomes stale.

```javascript
import useSWR from 'swr'

const fetcher = (...args) => fetch(...args).then((res) => res.json())

function Profile() {
  const { data, error } = useSWR('/api/profile-data', fetcher)

  if (error) return <div>Failed to load</div>
  if (!data) return <div>Loading...</div>

  return (
    <div>
      <h1>{data.name}</h1>
      <p>{data.bio}</p>
    </div>
  )
}

```

### 20.What is Server-Side Rendering in Next.js?

If you export a function called getServerSideProps (Server-Side Rendering) from a page, Next.js will pre-render this page on each request using the data returned by getServerSideProps.
```javascript
export async function getServerSideProps(context) {
  return {
    props: {}, // will be passed to the page component as props
  }
}
```

When does getServerSideProps run : getServerSideProps only runs on server-side and never runs on the browser. If a page uses getServerSideProps, then:

When you request this page directly, getServerSideProps runs at request time, and this page will be pre-rendered with the returned props

When you request this page on client-side page transitions through next/link or next/router, Next.js sends an API request to the server, which runs getServerSideProps

getServerSideProps returns JSON which will be used to render the page. All this work will be handled automatically by Next.js, so you don’t need to do anything extra as long as you have getServerSideProps defined.

You can use the next-code-elimination tool to verify what Next.js eliminates from the client-side bundle.

getServerSideProps can only be exported from a page. You can’t export it from non-page files.

Note that you must export getServerSideProps as a standalone function — it will not work if you add getServerSideProps as a property of the page component.


### 21.What is Static Site Generation in Next.js?
If you export a function called getStaticProps (Static Site Generation) from a page, Next.js will pre-render this page at build time using the props returned by getStaticProps.
```javascript
export async function getStaticProps(context) {
  return {
    props: {}, // will be passed to the page component as props
  }
}
```

### 22. When should I use getStaticProps in Next.js?

You should use **getStaticProps** if :
 
* The data required to render the page is available at build time ahead of a user’s request

* The data comes from a headless CMS

* The page must be **pre-rendered** (for SEO) and be very fast — **getStaticProps generates** HTML and JSON files, both of which can be cached by a CDN for performance

* The data can be publicly cached (not user-specific). This condition can be bypassed in certain specific situation by using a Middleware to rewrite the path.


### 23.What is Image Component and Image Optimization in Next.js?

The Next.js Image component, next/image, is an extension of the HTML <img> element, evolved for the modern web. It includes a variety of built-in performance optimizations to help you achieve good Core Web Vitals. These scores are an important measurement of user experience on your website, and are factored into Google's search rankings.
 
Some of the optimizations built into the Image component include :
 
* Improved Performance : Always serve correctly sized image for each device, using modern image formats

* Visual Stability : Prevent Cumulative Layout Shift automatically

* Faster Page Loads : Images are only loaded when they enter the viewport, with optional blur-up placeholders

* Asset Flexibility : On-demand image resizing, even for images stored on remote servers


### 24.What is Environment Variables in Next.js?

Next.js comes with built-in support for environment variables, which allows you to do the following:
 
* Use .env.local to load environment variables
* Expose environment variables to the browser by prefixing with NEXT_PUBLIC_

Default Environment Variables : In general only one .env.local file is needed. However, sometimes you might want to add some defaults for the development (next dev) or production (next start) environment.
 
Next.js allows you to set defaults in .env (all environments), .env.development (development environment), and .env.production (production environment).
 
.env.local always overrides the defaults set.

### 25.What is Routing in Next.js?

When a file is added to the pages directory, it's automatically available as a route.
 
The files inside the pages directory can be used to define most common patterns.
 
Index routes : The router will automatically route files named index to the root of the directory.
 
* pages/index.js → /
* pages/blog/index.js → /blog

Nested routes : The router supports nested files. If you create a nested folder structure, files will automatically be routed in the same way still.
 
* pages/blog/first-post.js → /blog/first-post
* pages/dashboard/settings/username.js → /dashboard/settings/username

Dynamic route segments : To match a dynamic segment, you can use the bracket syntax. This allows you to match named parameters.
 
* pages/blog/[slug].js → /blog/:slug (/blog/hello-world)
* pages/[username]/settings.js → /:username/settings (/foo/settings)
* pages/post/[...all].js → /post/* (/post/2020/id/title)

### 26.What is Docker Image in Next.js?

Next.js can be deployed to any hosting provider that supports Docker containers. You can use this approach when deploying to container orchestrators such as Kubernetes or HashiCorp Nomad, or when running inside a single node in any cloud provider.
 
* Install Docker on your machine
* Clone the with-docker example
* Build your container: docker build -t nextjs-docker .
* Run your container: docker run -p 3000:3000 nextjs-docker

If you need to use different Environment Variables across multiple environments, check out our with-docker-multi-env example.

### 27. What is Authentication Patterns in Next.js? 

The first step to identifying which authentication pattern you need is understanding the data-fetching strategy you want. We can then determine which authentication providers support this strategy.

There are two main patterns :
 
* Use static generation to server-render a loading state, followed by fetching user data client-side.
* Fetch user data server-side to eliminate a flash of unauthenticated content.

### 28.How can you create a page directory inside your project?

To create a page directory inside our project we have to populate the ./pages/index.js with the following contents:
```javascript
function HomePage() {  
  return <div>Welcome to Next.js!</div>  
}  
```

To start developing our application, we have to run the npm run dev or yarn dev command. This will start the development server on http://localhost:3000. Now we can visit the localhost: http://localhost:3000 to view our application.

### 29.Give an example to demonstrate how to create a custom error page in Next.js?
We can create our custom error page by defining a _error.js in the pages folder. See the following example :
```javascript
import React from "react";  
class Error extends React.Component {  
  static getInitialProps({ res, err }) {  
    const statusCode = res ? res.statusCode : err ? err.statusCode : null;  
    return { statusCode };  
  }  
  render() {  
    return (  
   
        {this.props.statusCode  
          ? `An error ${this.props.statusCode} has occurred on the server`  
          : "An error occurred on client-side"}  
        
    );  
  }  
}  
export default Error;​
```

### 30.What do you understand by code splitting in Next.js?

Generally, code splitting is one of the most compelling features of webpack. This feature facilitates us to split our code into various bundles, which can be loaded only on-demand or in parallel. This is mainly used to achieve the smaller bundles and facilitates us to control resource load prioritization which finally has a great impact on the load time.
 
There are mainly three approaches to code splitting :
 
  **Entry Points :** It is used to split code using entry configuration manually.

  **Prevent Duplication :** It uses Entry dependencies or SplitChunksPlugin to dedupe and split chunks.

  **Dynamic Imports :** It splits the code via inline function calls within modules

It is mainly used to enable pages that can never load unnecessary code.


### 31.What are some of the similarities between Next.js and Gatsby?

Many people consider Gatsby and Next.js the same thing mostly because they almost perform the same function. However, the two frameworks are different and feature a couple of similarities at first glance. They include:
 
* The two frameworks both generate highly performing websites
* Next.js and Gatsby develop SPA out of the box
* The two frameworks create websites that are SEO friendly hence ranking top on browsers
* Under both circumstances, the developers have extraordinary experiences


### 32. How to URL Imports in Next.js?

URL imports are an experimental feature that allows you to import modules directly from external servers (instead of from the local disk).
 
Warning : This feature is experimental. Only use domains that you trust to download and execute on your machine. Please exercise discretion, and caution until the feature is flagged as stable.
 
To opt-in, add the allowed URL prefixes inside next.config.js :
```javascript

module.exports = {
  experimental: {
    urlImports: ['https://example.com/modules/'],
  },
}
```
Then, you can import modules directly from URLs :

```javascript
import { a, b, c } from 'https://example.com/modules/some/module.js'
```

URL Imports can be used everywhere normal package imports can be used.


### 33.What is Static Optimization Indicator in Next.js?

When a page qualifies for Automatic Static Optimization we show an indicator to let you know.
 
This is helpful since automatic static optimization can be very beneficial and knowing immediately in development if the page qualifies can be useful.
 
In some cases this indicator might not be useful, like when working on electron applications. To remove it open next.config.js and disable the autoPrerender config in devIndicators:

```javascript
module.exports = {
  devIndicators: {
    autoPrerender: false,
  },
}
```
### 34.How to Build indicator in Next.js?

When you edit your code, and Next.js is compiling the application, a compilation indicator appears in the bottom right corner of the page.
 
**Note :** This indicator is only present in development mode and will not appear when building and running the app in production mode.
 
In some cases this indicator can be misplaced on your page, for example, when conflicting with a chat launcher. To change its position, open next.config.js and set the buildActivityPosition in the devIndicators object to bottom-right (default), bottom-left, top-right or top-left:
```javascript
module.exports = {
  devIndicators: {
    buildActivityPosition: 'bottom-right',
  },
}
```
In some cases this indicator might not be useful for you. To remove it, open next.config.js and disable the buildActivity config in devIndicators object :
```javascript
module.exports = {
  devIndicators: {
    buildActivity: false,
  },
}
```


### 35  [When to Use Server-Side rendering vs Static Generation in Next.js](https://dev.to/dmuraco3/when-to-user-server-side-rendering-vs-static-generation-in-nextjs-8ab)

