<template>
  <div class="container mx-auto h-full">
    <chat-message></chat-message>
    <chat-form></chat-form>
  </div>
</template>
<script >
import ChatMessage from './components/ChatMessage.vue';
import ChatForm from './components/ChatForm.vue';

export default {
  components:{
    ChatMessage,ChatForm
  },
  mounted() {
    console.log(`the component is now mounted.`)
   /*  const CLIENT_TOKEN = 'H6VQHV2KGBH4ZMDQBDTC74KS7GXPFRWJ'
    const q = encodeURIComponent('what day is it today?');
    const uri = 'https://api.wit.ai/message?v=20240304&q=' + q;
    const auth = 'Bearer ' + CLIENT_TOKEN;
    fetch(uri, {headers: {Authorization: auth}})
      .then(res => res.json())
      .then(res => console.log(res)) */
  }
}
</script>
<style scoped>

</style>
