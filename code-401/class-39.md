# Readings: React 3

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading

[NextJs](https://nextjs.org/learn/basics/getting-started)

-   Through `Assets, Metadata, and CSS` section.

To build a complete web application with React you need to consider:

-   Code has to be bundled using a bundler like webpack and transformed using a compiler like Babel.
-   You need to do production optimizations such as code splitting.
-   You might want to statically pre-render some pages for performance and SEO. You might also want to use server-side rendering or client-side rendering.
-   You might have to write some server-side code to connect your React app to your data store

Next.js aims to have best-in-class developer experience and many built-in features, such as:

- An intuitive page-based routing system
- Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
- Automatic code splitting for faster page loads
- Client-side routing with optimized prefetching
- Built-in CSS and Sass support, and support for any CSS-in-JS library
- Development environment with Fast Refresh support
- API routes to build API endpoints with Serverless Functions
- Fully extendable

[React Context for Beginners](https://www.freecodecamp.org/news/react-context-for-beginners/)

**These types of data include:**

-   Theme data (like dark or light mode)
-   User data (the currently authenticated user)
-   Location-specific data (like user language or locale

React context helps us avoid the problem of props drilling.

**Props drilling** is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.

There are four steps to using React context:

1. Create context using the createContext method.
2. Take your created context and wrap the context provider around your component tree.
3. Put any value you like on your context provider using the value prop.
4. Read that value within any component by using the context consumer.


Let's break down what we are doing, step-by-step:

1.  Above our `App` component, we are creating context with `React.createContext()` and putting the result in a variable, `UserContext`. In almost every case, you will want to export it as we are doing here because your component will be in another file. Note that we can pass an initial value to our `value` prop when we call `React.createContext()`.
2.  In our `App` component, we are using `UserContext`. Specifically `UserContext.Provider`. The created context is an object with two properties: `Provider` and `Consumer`, both of which are components. To pass our value down to every component in our App, we wrap our Provider component around it (in this case, `User`).
3.  On `UserContext.Provider`, we put the value that we want to pass down our entire component tree. We set that equal to the `value` prop to do so. In this case, it is our name (here, Reed).
4.  In `User`, or wherever we want to consume (or use) what was provided on our context, we use the consumer component: `UserContext.Consumer`. To use our passed down value, we use what is called the **render props pattern**. It is just a function that the consumer component gives us as a prop. And in the return of that function, we can return and use `value`.

## Videos

[Why I’m using Next.js in 2020](https://www.youtube.com/watch?v=rtgbaKBhdkk)
He thinks the future of React is Next.js
Talk about 5 things about next.js
1. background
2. performance
3. developer experience
4. deployment
5. community

next.js is a framework built ontop of react. Lets you choose if you want to render on client, dev or both sides.

[Learn useContext In 13 Minutes](https://www.youtube.com/watch?v=5LrDIWkK_Bc)
Context is for passing down props to all the children without having to actually pass them down to all the children
simplifies your code drastically, less nesting

The gist I got from this is that it's really simplifies your code and makes it more reusable.

## Bookmark and Review

[Next.js Examples](https://github.com/vercel/next.js/tree/canary/examples)