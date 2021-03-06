#Setting Up a React.js Environment Using Npm, Babel 6 and Webpack

https://www.codementor.io/reactjs/tutorial/beginner-guide-setup-reactjs-environment-npm-babel-6-webpack

```javascript
mkdir react-hello-world
cd react-hello-world
npm init
```

touch webpack.config.js

```javascript

var webpack = require('webpack');
var path = require('path');

var BUILD_DIR = path.resolve(__dirname, 'src/client/public');
var APP_DIR = path.resolve(__dirname, 'src/client/app');

var config = {
  entry: APP_DIR + '/index.jsx',
  output: {
    path: BUILD_DIR,
    filename: 'bundle.js'
  },
  loaders : [
      {
        test : /\.jsx?/,
        include : APP_DIR,
        loader : 'babel'
      }
    ]
};

module.exports = config;

```

npm i babel-loader babel-preset-es2015 babel-preset-react -S




touch .babelrc
```javascript
{
  "presets" : ["es2015", "react"]
}
```

./node_modules/.bin/webpack -d --watch
