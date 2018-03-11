# Modern Social Network - React, React Native &  Express

A completed guide on how to build a **FULL-STACK** modern **SOCIAL NETWORK** with a **WEBSITE & MOBILE APP**.

## Tech Stack
- **React** - website 
- **React Native** - mobile app - iOS & Android
- **Express** - server
- **Postgres** + **Sequelizer** - database

## Guide

### Step 1:
- Create a (private) **Github repo** for the **web app & server**
- Call it **`social-app-web`**

### Step 2:
- Create a simple **Express server**. Follow this [guide](https://expressjs.com/en/starter/hello-world.html)

### Step 3:
- Create a simple **React app with Webpack**
    - Don’t user CRA cause we don’t need the tooling around it such as custom `react scripts` etc
    - We are going to use `Webpack` instead for our React frontend app to talk to our Express backend
    - Create a folder called `client/src/app.js` (copy a simple React App example with Hello world into it)
    - `npm install --save react react-dom react-router webpack` (dependency)
    - also `npm install --save -D babel-core, babel-loader & style-loader, file-loader, url-loader, node-sass, css-loader & sass-loader, babel-preset-react, babel-preset-es2015` for webpack config (dev-dependency)
    - Then we need to create a `webpack.config.js` to configure our webpack and serve React files
    - Then finally add scripts in your `package.json` and test the React app
    
### Step 4:
- Connect the **React app with Express server**
	- Create a `server/static` folder with an `index.html` file. By default Express will look for and render this file.
    - And in this file we have `div` with an `id`. And this is the same `id` we give to our react app. So the entire React JS app will render in that 1 div and it will work with the virtual DOM.
    - Start the express server `yarn start` and test a simple `/api` endpoint
    - Build webpack `yarn build` and test the React app


### Step 5:
- **Deploy** the **React + Express app** to **Heroku**
    - Add a `LandingPage` component to your React app
    - Add file `webpack.prod.config.js` and add webpack production config scripts for heroku deploy: `"build": "NODE_ENV=production webpack --config ./webpack.prod.config.js --progress --colors"`
    - Add `heroku-postbuild` script to `package.json` & generate will generate the app bundle file on Heroku: `"heroku-postbuild": "yarn --production=false && yarn build"`
    - Change Express `index.js` file to serve conditonally @ `heroku url` or `localhost`
    - Deploy the Express app to Heroku. Follow this [guide](https://devcenter.heroku.com/articles/deploying-nodejs)


### Step 6:
- Create a (private) **Github repo** for the **mobile app**
    - Call it **`social-app`**

### Step 7:
- Create a simple **React Native app**
  - Use Expo to generate a new app

### Step 8:
- Add **screens & API call** to React Native app
    - Create the Intro, Login, Sign Up, Social & Profile screens
    - Add a simple API call to server `/api => returns “hello world"`

### Step 9:
- Create the **`/auth/` endpoints** on server **for signup & login**
    - need to add `morgan` (logger) & `body-parse` (to parse post body) & `validator`
    - create `server/routes/auth.js` folder and add two `router.post endpoints` for `/signup` & `/login`
    - for now you can return dummy data with the correct status
    - test the endpoints using postman or ideally using the mobile app

### Step 10:
- Add **`navigation`** to the React Native app
    - build post detail screen, edit profile screen & create post screens
    - setup all the screens with dummy data & connect it with navigation

### Step 9:
- Setup **postgres & sequelizer** for the express server
    - Create a CRUD express app with postgres & sequelizer. Follow this [guide](https://scotch.io/tutorials/getting-started-with-node-express-and-postgres-using-sequelize#sequelize-setup)
    - create `user` & `post` db tables
    - generate controllers & routes for `user` & `post` data - CRUD actions

### Step 10:
- Push `/api/` changes to Heroku & **deploy production DB**
    - Add `postgres add-on` to Heroku app
    - Add `postinstall` script command on `package.json`: `"postinstall": "npm install -g sequelize-cli && sequelize db:migrate",`
    - Add production DB config in `/server/config` with `"use_env_variable": "DATABASE_URL"`
    - And that’s it! :tada: You should be able to see the logs that it migrated & that the db is live with the new tables
    - Then open the heroku db on your mac with postico - use heroku cli - and check to see if the data is being stored correctly in the db
    - if it throws an error - check `logDNA` logs and you can try to debug it


<br />

Authored by [**Monte Thakkar**](https://github.com/monte9)

Last updated: **March 2018**

