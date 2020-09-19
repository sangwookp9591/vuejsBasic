<template>
  <div><!-- 템플릿이라는 속성은 html element가 최상위 레벨에 하나만 있어야한다. 밑에 추가하면 안되고 그다음부터 안에 추가해야함.-->
     <!-- <app-header v-bind:프롭스 속성이름="상위 컴포넌트이 데이터 이름"></app-header> -->
     <!-- App이라는 컴포넌트에서 str이라는 데이터를 propsdata로 내려보는것  -->
     <!-- <app-header v-on:하위컴포넌트에서 받은 데이터 이름="실행할 메소드이름"></app-header> -->
     <app-header 
     v-bind:propsdata="str"
     v-on:renew="renewStr"
     ></app-header>
    
  </div>
</template>

<script>
/*
정의한 동작의 순서

 component에 내용정의하고 변수에 넣음
 Var AppHeader = { 
   template:'<header><h1>Header</h1></header>'
 }
  와 같음.
  위와같이 객체로 저장한게아니라 파일의 내용을 불러올 수 있는 import from 이라는 문법을써  components에 바로 연결


*/
Vue.config.devtools = true;
import AppHeader from './components/AppHeader.vue'; //상대경로이기ㅣ때문에 같은 위치에서 ./components (해당 AppHeader의 내용이 AppHeader에 담겨있다.
// 즉 import로 들고온 파일을 AppHeader라는 변수에 담음것)
/*
기존방식 
new Vue({
  data: {
    str: 'hi'
  }
});
*/
export default {
  data: function() {
    return  {
      str: 'Header'
    }//.vue파일은 컴포넌트를 재사용할 확율이 높고 여러개의 컴포넌트에서 동일한값을 참조하면 안되기때문에 fuucntion을하고 안에서 새객채를 리턴하는 방식으로 사용해야한다.
  },
  components: {
    'app-header': AppHeader //컴포넌트 이름 : 여기서 AppHeader는 import로 들고온 변수를 연결한것
  },
  methods: {
    renewStr: function(){
       this.str = 'hi' // 이메소드가 변경됫기때문에 다시한번 str이 appheader로 전달되며 값이 변경된걸 확인할  수 있다.
    }
  }
}
</script>

<style>

</style>