# qi-px2vw-loader
A webpack loader, transfer px to vw in stylesheet.
## Install 
``` 
npm install qi-px2vw-loader --save-dev
```

## Examples
### 1. Transform px to vw in css  
webpack configs: 
``` 
  module: {
    rules: [{
      test: /\.css$/i,
      use: [
        {loader: 'style-loader'},
        {loader: 'css-loader'},
        {
          loader: 'qi-px2vw-loader',
          options: {
            // exclude some files which need not tranform
            exclude: /node_modules/
          }
        }
      ],
    }]
  }
````

### 2. Transform px to vw in sass:  
webpack configs: 
``` 
  module: {
    rules: [{
      test: /\.s[ac]ss$/i,
      use: [        
        {loader: 'style-loader'},
        {loader: 'css-loader'},
        {loader: 'sass-loader'},
        {loader: 
          loader: 'qi-px2vw-loader',
          options: {
            exclude: /node_modules/
          }
        }
      ],
    }]
  }
```

### 3. Transform px to vw in vue:   
webpack configs: 
``` 
  module: {
    rules: [{
      test: /\.vue$/,
      loader: 'vue-loader',
      options: {
        loaders: {
          css: ['vue-style-loader', 'css-loader', {
            loader: 'qi-px2vw-loader'
          }],
          scss: ['vue-style-loader', 'css-loader', 'sass-loader', {loader: path.resolve(__dirname, './loaders/px2vw')}]
        }
      }
    }]
  }
```



