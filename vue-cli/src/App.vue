<template>
  <div><!-- 템플릿이라는 속성은 html element가 최상위 레벨에 하나만 있어야한다. 밑에 추가하면 안되고 그다음부터 안에 추가해야함.-->
     {{ hi }}
  </div>
</template>

<script>
//.vue파일은 컴포넌트를 재사용할 확율이 높고 여러개의 컴포넌트에서 동일한값을 참조하면 안되기때문에 fuucntion을하고 안에서 새객채를 리턴하는 방식으로 사용해야한다.
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
      str: 'hi'
    }
  }
}
</script>

<style>

</style>