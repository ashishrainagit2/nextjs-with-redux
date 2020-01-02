# nextjs-with-redux

##Version 1 ##

This project version one: shows a simple two files 1._app.js and 2. index.js to add redux to nextjs

Steps:
1. mkdir folderNameOfYourChoice
2. cd folderNameOfYourChoice
3. npm init -y
4. npm i react react-dom next@v9.0.9-canary.0 next-cookie axios cookie-parser express js-cookie next-redux-wrapper react-redux redux redux-thunk
5. mkdir pages
6. touch pages/index.js
7. touch server.js

8. Update your package.json so that we can run in dev, build and start in production as well.

// package.json
"scripts": {
    "dev": "node server.js",
    "build": "next build",
    "start": "NODE_ENV=production node server.js"
  },
  
 9. Next step is to create server.js in the root of your project. Here we will use express to create a server. Then pass all incoming requests (using wildcard *) to next for further handling.
10. Now you can run npm run dev in your terminal and see you app in localhost:3000

Setting up redux with next js
Next.js uses the App component to initialize pages. You can override it to control what your pages will receive as props during initialization. You can do so using getInitialProps method in your pages. Lets create _app.js inside pages folder so that we can override the default App component of next js. We are doing this to be able to pass props(properties) from redux store to other pages. This way pages will be able to access redux store as props.

What is getInitialProps in next js?
getInitialProps is one of the core feature of next js. This method runs on both client side and server side. On first initial loading of page, getInitialProps runs in server side. Then onwards it runs on client side.

There are differences on what params you can destructure in getInitialProps method inside pages and _app.

While inside pages you can destructure pathname(path of url), query(query string of url), asPath(string of url path including query), req(server side), res(server side), jsonPageRes(client side for fetch response object) and error in getInitialProps({pathname, query, asPath, req, res, jsonPageRes, err})

While inside _app you can destructure Component, router and ctx(context) in getInitialProps({ Component, router, ctx })

Link: https://kaloraat.com/articles/next-js-react-redux-authentication-tutorial
