# Next.js

Allows to build FULLSTACK app with React.js

# Features and Benefits -

- FullStack Apps (Next.js blends frontend + backend in same project).
    
    Advantage - Frontend and backend tasks are part of the same project
    
- FileSystem based Routing -
    - Routes are configured via the filesystem (folders + files)
    - Advantage - No code-based configuration or extra packages for routing are required.
- Server-side Rendering
    - By default NextJS (pre-) renders all pages on the server.
    - Advantage - The finished HTML page (including content) is sent to the client (great for SEO)


# Two Approaches for building NextJS apps

### 1. Pages Router

- Has been around for many years
- Very stable
- Used in many existing Nextjs projects
- Allows to build fullstack apps

### 2. App Router

- Introduced in NextJS 13
- Marked as stable but relatively new and partially buggy
- Supports modern Next & React features (fullstack React apps)
- The future of NextJS

## Creating NextJS APP

Command to create app

`npx create-next-app@latest`

Using App Router method -

When using AppRouter method an `app` folder is created in folder structure.

Structure is something like this

- app
- public

`app` folder is used for routing in Next JS

## Reserved keywords for filenames in Next (only in app folder)

`page.js` - Create new page (eg. app/about/page.js)

`layout.js` - Create a new layout that wraps sibling and nested pages

`not-found.js` - Fallback page for “Not found” errors (thrown by sibling or nested pages or layouts)

`error.js` - Fallback page for other errors (thrown by sibling pages or nested pages or layouts)

`loading.js` - Fallback page which is shown whilst sibling or nested pages (or layouts) are fetching data.

`route.js` - Allows you to create an API route (i.e. page which does not return JSX code but instead data eg. in JSON format)


## Creating Routes in Next JS

Names of files are important in NextJS

The page name should be `page.js`

New folder should be created for each new route in `app` folder

So to create `/about` route about folder should be created.

And inside each route there should be a `page.js` file

Below is example of folder structure -

- app
    - about/
        - `page.js`
    - contact/
        - `page.js`
    
    `page.js` 
    

To create link for a page use `Link` component provided by Next js instead of `a` tag. Because when `a` tag is used a new page is given by the server and we do not get the single page app functionality.


## Dynamic Routing in Next

Suppose we have a `/blogs` page in our `app` folder. We cannot create a seperate folder for each blogpost. like `/blog/post1`   `/blog/post2` . This is not scalable.

To do this dynamic routing in Next JS, it provides a syntax to create dynamic routes.

Something like this

- app
    - blogs
        - [ <any identifier> ]
            - page.js
        - page.js
    - page.js

So we can create folder using `[]` brackets and put any identifier inside it, and then create `page.js` inside which will work as dynamic route page. 

```jsx
// blogs/page.js

export default function Blogs(){
	return(
		<Link href='/post-1'>Post 1</Link> // url: /blogs/post-1
    <Link href='/post-2'>Post 2</Link> // url: /blogs/post-2
	)
}
```

When we click on any of the links above it will redirect to dynamic posts page

```
// blogs/[postId]/page.js

// postId passed in URL can be accessed using params.postId
export default function Blogs({params}){
	return(
		<p>Post name - {params.postId}</p>  //post-1 or post-2
	)
}
```