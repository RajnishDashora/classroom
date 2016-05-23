### Setting up react-storybook in your project : 

 **1. `npm i --save-dev @kadira/storybook`**
 **2. `npm i --save-dev webpack-hot-middleware`**
 **3. Change, in `package.json`** 
```
{
  ...
  "scripts": {
    "storybook": "start-storybook -p 9001"
  }
  ...
}
```
**4. Change, in `karma.conf.js`**
```
loaders: [{
          ...
          exclude: [
          	/node_modules/,
          	/\-story\.js/
          ],
          ...
        },
```
**5.  `mkdir .storybook` in project root directory.**
**6.  Add, `.storybook/config.js`**
```
import { configure } from '@kadira/storybook';

const req = require.context('../test/components/', true, /\-story\.js/);

function loadStories() {
	 req.keys().forEach(req);
}

configure(loadStories, module);

```
If you want your stories to be in the same directory as of your test case you can use the following configuration. Also the regular expression can be modified as the your project structure. 
**7. Add, `.storybook/webpack.config.js`**
```
const path = require('path');
var webpack = require('webpack');
// Setup our plugins.
var plugins = [
  new webpack.DefinePlugin({
    __ENV__: JSON.stringify(process.env.NODE_ENV || 'dev')
  })
];
module.exports = {
  module: {
    loaders: [
      {
      	test: /\.scss/,
      	loader: 'style!css!autoprefixer!sass?outputStyle=expanded',
        include: path.resolve(__dirname, '../')
      },{
      test: /\.css$/,
      exclude: [/\.raw\.css$/, /\.useable\.css$/, /node_module/],
      loader: 'style!css!autoprefixer',
        include: path.resolve(__dirname, '../')
    }, {
      test: /\.useable\.css$/,
      loader: 'style/useable!raw!autoprefixer',
        include: path.resolve(__dirname, '../')
    }, {
      test: /\.raw\.css$/,
      loader: 'style!raw!autoprefixer',
        include: path.resolve(__dirname, '../')
    }, {
      test: /\.(gif|png|jpg)$/,
      loader: 'url?limit=8192',
        include: path.resolve(__dirname, '../')
    }, {
      // handle woff web-fonts, for the custom TSEL iconfonts
      test: /\.woff(2)?(\?v=[0-9]\.[0-9]\.[0-9])?$/,
      loader: "url-loader?limit=10000&minetype=application/font-woff",
        include: path.resolve(__dirname, '../')
    }, {
      // handle other supported web-fonts, for the custom TSEL iconfonts
      test: /\.(otf|ttf|eot|svg)(\?v=[0-9]\.[0-9]\.[0-9])?$/,
      loader: "file-loader",
        include: path.resolve(__dirname, '../')
    },
    ]
  },
  plugins: plugins

}

```    
8. Start adding stories(-story.js prefix if you use the same configs) to your components. please refer ***https://github.com/kadirahq/react-storybook***
Adding a patch which can be used to for the above changes. 
