# Event 상속

* 부모에서 넘길때

```javascript

//부모에서 자식 넘길 때
"v-bind" or ":" 로 props를 넘길 수 있다.
함수의 경우 @넘길 함수 이름="정의한 함수 이름"

<Modal
    :show = "showModal"
    :point = "this.point"
    @close = "handlePointsStorageClose"
/>

data(){
    return {
        showModal : false,
        point : 1000
    }
},
methods:{
    handlePointsStorageClose(close){
        this.showShortageModal = close;
    }
}
```

* 자식에서 부모로 

```javascript

<script>

export default {
  //1. 먼저 아래와 같이 props로 받은 정보가 어떤 자료형인지 정의합니다. 정의한 경우 정의된 자료형과 다른 자료형의 데이터가 들어오면 warning을 console에 띄웁니다.
  props: {
    show: Boolean,
    point: Number,
    close: Function
  }
};
</script>
<template>
  <div>
    <!--2. prop으로 받은 point는 아래와 같이 templete에서는 point로 script에서는 this.point로 사용합니다.-->
    <p>포인트 : {{ point }}P</p>
    <!--3. 부모로 받은 함수는 templete에서는 $emit()으로 script에서는 this.$emit()으로 사용합니다.
    첫번째 인자로는 부모로 받은 인자(@close)인 close를 사용하고 두번째 인자는 부모 컴포넌트의 함수의 첫번째 인자로 들어갑니다. (close) -->
    <Button @click="$emit('close', false)">
      닫기
    </Button>
  </div>
</template>


 
```