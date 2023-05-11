## Set Up
Use the scaffolding tool [Vite](https://vitejs.dev/guide/) to create your starter code. You can run these commands to get started:

```sh
# Check your npm version
npm -v 

# npm 6.x
npm create vite@latest project-name --template react

# npm 7+, extra double-dash is needed:
npm create vite@latest project-name -- --template react

cd project-name
npm i
npm run dev
```

# Open Project: useEffect and useContext

This project focuses on demonstrating these React skills:

1. Creating controlled forms
2. Using the `useEffect` hook to execute an asynchronous `fetch` from a public API.
3. Rendering a list of data as a list of components
4. Using the `createContext` function and the `useContext` hook to manage the global state of your application.

Think of this as a mini project-week solo-project (but you can certainly collaborate to get it done!). 

## Features

How you choose to build this project is up to you, but it must include the features below:

Think of these features as a check-list of your skills. Work on them from top to bottom and make note of the functionality that you're struggling to implement.

- (1pt) Your components are each isolated in separate files within a `src/components` folder. 
   *  Each file should have one `export default`.
   *  Use `import DefaultExportValue from './relative/path/to/file'` syntax
- (1pt) You have a controlled form component with at least one text input. 
   * The form should use `useState()` to constantly track the value in the text input element. 
   * You can demonstrate this by printing to the console the value of the input form whenever the value changes (`onChange`).
* (1pt) When a user first visits your application, data is fetched from an application using a `fetch` call within a `useEffect` hook.
   * The API you use is up to you but here are a few good ones: [Giphy API](https://developers.giphy.com/docs/api/#quick-start-guide), [PokeAPI](https://pokeapi.co/), [NYT API](https://developer.nytimes.com/apis), or check out this [list of free APIs](https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/)
   * Whatever data you fetch, it must return a collection (an array) of items, rather than a single value.
   * You can demonstrate this by printing to the console the array of data retreived from your `fetch` call. Make sure that the array of data you fetch contains at least 3 values
* (1pt) Whenever data is fetched from your chosen API, at least 3 values from your fetched dataset are rendered.
   * For example, when fetching from the Giphy API using the API, an array of objects like this will be returned (and more actually)
      ```js
      {
        "type": "gif",
        "id": "bCPW72z0z0OhmSvD54",
        "username": "ballysportsdetroit",
        "title": "Happy Detroit Tigers GIF by Bally Sports Detroit",
        "images": {
          "original": {
            "height": "270",
            "width": "480",
            "size": "1403918",
            "url": "https://media3.giphy.com/media/bCPW72z0z0OhmSvD54/giphy.gif?cid=3836d4808jt6j3jjuj3wmt74qrnro6g3p8u10p7dcdzlmoq6&ep=v1_gifs_trending&rid=giphy.gif&ct=g",
      }
      ```
   * If you were to use this API, your application would fetch at least 3 of these objects and could render the `title` and the `images.original.url` for each.
   * Each value from your fetched dataset should be rendered as a custom React component. For example, you could define a component called `Gif` with `title` and `url` props. You would then render one `<Gif title={} url={} />` for each value in the dataset.
   * You can demonstrate this feature by refreshing your page and seeing at least 3 UI components rendered to show the fetched data.
* (1pt) The `useEffect` fetch is executed whenever the input form value changes. 
   * Each useEffect fetch should also update the rendered list of components.
   * You can demonstrate this by typing in the text input of your form and see new data populating on your page
* (1pt) Establish a global context for your application such that data is shared between your components.
   * Your context should implemented using two files: one file where the context is created and exported, and one file where the `ContextProvider` component is exported with values.
   * If you have not already done so, refactor your code such that `ContextProvider` contains your `useEffect` hook.
   * The `ContextProvider` component should wrap the top-level `App` component
   * The global state of the application should be managed by the `ContextProvider`
   * Components that need to use state or state-setter functions can retrieve them from the context using the `useContext` hook.
   * You can demonstrate this by having a fully function application. Check with your instructor for best practices, or compare your code with an exemplar solution.

## Grading

In terms of grading, completing each feature will earn you 1 point and your total score will be a percentage out of the total possible points you can earn. As such, you should be able to self-grade and identify your own areas of growth (though we will help with that too).

# Giphy Search Example

If you want an example of a project to build, consider this Giphy Search project.  For further assistance, see this [starter-code repo](https://github.com/The-Marcy-Lab-School/giphy-search-vite/tree/main) which contains a pre-built Vite project with the skeleton of some components already defined for you. You are free to copy anything you want from this project.

![demo](./demo.gif)

## Features

1. When a user first load the app, they should see 3 gifs from today's [Trending Gifs](https://developers.giphy.com/docs/api/endpoint#trending) **as an unordered list**.
2. The user should be able to [search for gifs](https://developers.giphy.com/docs/api/endpoint#search). You app should update the gifs on the page, displaying 3 at a time, **every time the user clicks the Find Gifs button**. 

## API 

You will be using the [Giphy API](https://developers.giphy.com/docs/api#quick-start-guide) and will need to register for an API key.

The endpoints you can use are:

```
https://api.giphy.com/v1/gifs/trending?api_key={API_KEY}&limit=3&rating=g
```

```
https://api.giphy.com/v1/gifs/search?api_key={API_KEY}&q={query}&limit=3&rating=g
```


