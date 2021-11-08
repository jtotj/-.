# ES6 for vue
> Intro

## Babel
* 구 버전 브라우저 중에는 ES6의 기능을 지원하지 않는 브라우저가 있으므로 ES6 -> ES5로 변환해주는 컴파일러

```javascript

module: {
    loaders: [{
        test: /\.js$./,
        loader: 'babel-loader',
        query: {
            presets: ['es2015']
        }
  	}]
},

```

* 나중에 자세히 다룰 것


## For in, For of

