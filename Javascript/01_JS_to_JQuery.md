# ES6 for vue
> Intro

---

## Babel
* 구 버전 브라우저 중에는 ES6의 기능을 지원하지 않는 브라우저가 있으므로 ES6 -> ES5로 변환해주는 컴파일러
    * 바벨 온라인 에디터    https://babeljs.io/repl/   
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

---

## For in, For of, ForEach

```javascript

let obj = {
    a : 1,
    b : 2,
    c : 3
}

for (let item in obj){
    //object 반환
}

let arr = [1,2,3] 

for(let item of arr){
    //array 반환 but for in 시 index  반환
}

let arr2 = [1,2,3]

arr2.forEach( value => console.log(value))

```

---


## Modules

```javascript
//lib/scroll.js
export function scrollDispatch(pos){
    return pos;
}

//main.js

import { scrollDispatch } from 'libs/scroll.js';
scrollDispatch(target.scrollTop)

```

* vue.js에서의 `default` export
    * default 키원드가 붙으면 한개의 파일에서 하나 밖에 export 되지 않는다.

```javascript
    //utill.js
    export default function(data)
    {
        return console.log(data);
    }

    //main.js
    import someName from 'utill.js'
    console.log(someName) // function(data){return console.log(data)}

    //use
    someName('mydata');

```

---

## 뷰엑스에서 Object Spread Operator 적용예시
<br>

* state 속성 선언 부분

```javascript
// store.js 
new Vuex.Store({
    state: {
        prop1: ...,
        prop2: ...,
        prop3: ...
    }
});
```
```javascript
// app.js
new Vue({
    computed: {
        prop1() {
            return store.state.prop1;
        },
        prop2() {
            return store.state.prop2;
        }
        ...
    }
});
```

* 뷰엑스에서 제공하는 mapState함수를 이용하면 위 코드처럼 `state`에 일일이 접근하지 않아도 된다.
```javascript
import { mapState } from 'vuex';

var state = mapState(['prop1', 'prop2', 'prop3']);
```
* mapState에 `...`연산자를 붙여 computed 속성에서 쉽게 뷰엑스의 state에 접근할 수 있다.

```javascript
// app.js
import { mapState } from 'vuex';

new Vue({
    computed: {
        someLocalComputedProp() { ... },
        ...mapState(['prop1', 'prop2', 'prop3'])
    }
});
```