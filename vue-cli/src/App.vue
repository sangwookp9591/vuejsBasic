<template>
  <form v-on:submit="submitForm"> <!--폼은 어떤 정보를 전덜하고 넘어가는 특성이 있음.-->
    <div>
      <label for="username">ID: </label>
      <input id="username" type="text" v-model="username"><!--input 에 어던값이 입력될때마다 바로 username에 반영 userame의 내용을 화면에 바로 보여주는 to-a databinding-->
    </div>
    <div>
     <label for="password">PW:</label>
      <input id="password" type="password" v-model="password">
    </div>
    <button type="submit" >login</button> <!--submit이기 때문에 새로고침이된다.-->
  </form>
</template>

<script>
export default {
  data: function(){ //컴포넌트단위로 개발할때는 컴포넌트의 데이터가 참조되어 공유되지 않게 data function에서 새객체를 리턴하는 방식으로 사용
    return{
      username: '',
      password: '',
    }
  },
  methods:{
    //폼은 어떤 정보를 전덜하고 넘어가는 특성이 있음. 이걸 막기위해서 event라는 인자를받아서
    
    submitForm: function(event){
      event.prventDefault();// 를사용 폼의 이동 새로고침을 막는다.,
      console.log(this.username, this.password);
    }
  }
}
</script>

<style>

</style>