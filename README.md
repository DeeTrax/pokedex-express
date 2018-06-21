# Pokedex Express App

We will build our first web app using Node.js and Express - a Pokedex app.

For this exercise, we will be setting up express to intercept incoming requests on certain routes, reading data from a JSON file, and responding to HTTP requests with simple strings, JSON, or full HTML pages.

## Getting Started

1.  Fork and clone this repository to your computer
2.  Run `npm install` to install dependencies
3.  Look in the starter file called `index.js`. This will be the entry-point to your app
4.  Run `node index.js` to start a local server on port 3000
5.  Open `localhost:3000` on your browser and see the home page

Additionally, to improve your workflow, install the `nodemon` package. Nodemon helps us restart our local server every time it detects a "save" event on `index.js`. Neat stuff.

```
# install nodemon in Terminal
npm install -g nodemon

# run nodemon to start server
nodemon index.js
```

#### Note on comments:

The comments in this file are deliberately verbose meant to orientate you to an Express app for the first time. Feel free to remove any or all comments.

## Deliverables

Use the data in `pokedex.json` and return a response with details about the requested Pokemon. Specifically:

* Go through `pokedex.json` to understand how the data is structured. Where are all the pokemon data stored? (As usual, using a JSON parser for human-readable JSON is a good idea. There are many, [here](http://jsonprettyprint.com/) is one.)

* Return a string response with the requested pokemon's information when a request comes with matching the route `/some-name` (eg. `localhost:3000/bulbasaur` should show Bulbasaur's information - for now, show only its weight value)

* Modify your response for `/some-name` to return a HTML page (instead of just a string) with a `h1` tag that displays the name of the pokemon being requested, and a `ul` displaying its weight (eg. "Weight: 10 kg")

* Handle the case where an invalid pokemon name is provided (eg. `/some-name`). Return a HTML page with a `p` tag that says "Could not find information about `<pokemon_name>` - Is that a new pokemon? Gotta catch em' all!" (replace `<pokemon_name>` with the requested for pokemon name) Set the status code to 404.

## Further

* detect if the user didn't put anthing in the path. Return a HTML page with a `h1` tag saying "Welcome to the online Pokdex!" and a `ul` displaying _all_ the pokemon that exist in the pokedex

* Instead of showing just the weight, show all the details of the requested pokemon for `/some-name` route, adding each detail as a `li` to the `ul`

* Expose a new route for `/type/some-type` that returns a HTML page with a `ul` listing the names of all pokemon that have the specified type (eg. `/type/grass` should show a page with names of all pokemon of grass type). Format it however you like on the page.
