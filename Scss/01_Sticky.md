# Sticky
> Sticky는 자신이 속해 있는 곳의 높이에 영향을 받는다.
> Support Check https://caniuse.com/css-sticky


```css
/* 부모의 height는 설정 되어있어야 한다. 
height: xx% 동작안함*/
height: auto
height: unset
height: 100vh
height: 1000px
height: 5em

/*
부모 또는 조상 노드에 overflow 설정 시 동작 안함.
*/
overflow: hidden
overflow: scroll
overflow: auto

```

* 브라우저 Dev tool에서 아래 코드를 실행해서 조상노드에 overflow 설정 되어있는지 확인 가능
```javascript

//sticky element selector에 sticky 속성을 사용하고자하는 엘리먼트의 selector 설정
let parent = document.querySelector('[sticky element selector]').parentElement;

while (parent) {
  const hasOverflow = getComputedStyle(parent).overflow;
  if(hasOverflow !== 'visible') {
    console.log(hasOverflow, parent);
  }
  parent = parent.parentElement;
}

```