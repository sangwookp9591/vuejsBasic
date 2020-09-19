<template>
  <header>
      <h1> {{propsdata}}</h1>
      <button v-on:click="sendEvent">send</button>
  </header>
</template>

<script>
export default {
    props: ['propsdata'],
    methods: {
        sendEvent: function(){
            this.$emit('renew'); // this.$emit('');을 하게되면 ''안에 정의된 이벤트가  위쪽 component App.vue component로 전달됨.
        }
    }
}
</script>

<style>

</style>