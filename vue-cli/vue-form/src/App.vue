<template>
  <!-- <form v-on:submit="submitForm"> 폼은 어떤 정보를 전덜하고 넘어가는 특성이 있음. -->
  <form v-on:submit.prevent="submitForm"><!--event.prventDefault();와 같은의미 event modifier라고해서 submit에서 막겠다라는 의미. -->
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
import axios from 'axios';

export default {
  data: function(){ //컴포넌트단위로 개발할때는 컴포넌트의 데이터가 참조되어 공유되지 않게 data function에서 새객체를 리턴하는 방식으로 사용
    return{
      username: '',
      password: '',
    }
  },
  methods:{
    //폼은 어떤 정보를 전덜하고 넘어가는 특성이 있음. 이걸 막기위해서 event라는 인자를받아서
    
    
  submitForm: function(){
    // submitForm: function(event){
      //event.prventDefault();// 를사용 폼의 이동 새로고침을 막는다., javascript나  jquery에서 제공하는 방식
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users';
      //todo말고 users로 바꾸면  rest api 규칙에 의해 이 url로 보내고 데이터를 받을 수 있음.
      var data = {
        username: this.username,
        password: thos.password
      }
      axios.post(url,data)//브라우저에서 서버로 데이터를 주고받기 위한 라이브러리.
      //post 는 데이터를 생성하고 조작하기 위한 것
        .then(function(resopnse){
          console.log(response);
        })
        .catch(function(error){
          console.log(error);
        });
    }
  }
}
</script>

<style>

</style>