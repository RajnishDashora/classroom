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
The webpack config should look something like this, Also the regular expression can be modified as the your project structure. 
**7. Add, `.storybook/webpack.config.js`**
```

require('babel-register')({
  "presets": ["es2015"]
});
const WPC = require(`${base_path}/webpack.config.js`).default;
const webpackConfig = {
  module: {
    loaders: WPC.module.loaders
  }
};
module.exports = webpackConfig; 
```    
8. Start adding stories(-story.js prefix if you use the same configs) to your components. please refer ***https://github.com/kadirahq/react-storybook***
Adding a patch which can be used to for the above changes. 

Please note that we also need to ignore the story files from coverage of the project. 
