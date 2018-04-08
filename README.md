Full Stack JS project

1. Set Up

 Here we are doing it from the scratch.

Setting up the global Dependencies

a) First initialize package.json using npm init

b) npm install --save express for express servers

c) npm install --save mongodb for connecting to mongo db

d) npm install -S react react-dom for front end


Setting up the Dev dependencyies

1. npm install --save-dev webpack  for moduling the code

2. Babael is a tranfromer we will be using and for the trnspiler

   npm i -D babel-cli
   npm i -D babel-loader
   npm i -D babel-preset-es2015
   npm i -D babel-preset-stage-2
   npm i -D babel-preset-react

3. When we change anything in the node project restart is necessary. So we will be instlling the nodemon for auto restarting the node engine on saving the file.

  npm install --save-dev nodemon

4. Es Lint

  npm i -D eslint
  npm i -D eslint-plugin-react
  npm i -D babel-eslint

5. Creating Initial Directory Structure for the files.

  mkdir src for all the code
  mkdir public for all the static components like hTML js and CSS
  mkidir api for all our backend code

We will be adding the index files in all the folder for basic setup uses

6. Creatng Scripts

In the package.json folder add  Scripts

  "scripts": {
    "start": "node server.js"
  }

But our changes is driven by the nodemon so we will be appending the nodemon

"scripts": {
    "start": "nodemon --exec babel-node server.js"
  },

Aslo we need to ignore the public folder as it is driven by the crc folder changes

"scripts": {
    "start": "nodemon --exec babel-node server.js --ignore public/"
  },

To transform the src file to the webpack bundled file

"scripts": {
   "start": "nodemon --exec babel-node server.js --ignore public/" ,
   "dev": "webpack -wd"  // works with watch and dev mode.
  },


7.  Webpack Configuration

In This we tell webpack to start from the index file under the src directory and paste it in the output path in the public folder as the bundle.js

We will also run babel loader for all the files in the folder to transpile

8. babel coniguration

Create a file .babelrc under the root directory and add

{
  "preset": ["react", "es2015", "stage-2"]
}

This tells babel to all these presets
