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