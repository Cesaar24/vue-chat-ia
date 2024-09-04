<template>
  <div class="message mx-auto w-3/4 h-5/6 overflow-y-scroll ">
    <div
      v-for="(msg,i) in msgs" 
      :key="i"
      class="flex my-4 "
      :class="{'flex-row-reverse': msg.isAuthor }"
    >
      <figure 
        class="min-w-20"
      >
        <img :src=" msg.isAuthor ? '/user-blue.png' : '/star_favorite.png'" alt="" class="mx-auto">
      </figure>
      
      <div class="rounded-md my-4 p-3 content-center bg-cyan-700 overflow-hidden max-w-96">
        <span class="text-white text-xs md:text-base xl:text-lg sm:text-sm">{{msg.msg}} Lorem ipsum dolor sit amet consectetur adipisicing elit. In libero quas excepturi exercitationem delectus nisi sunt harum accusantium, minus dicta. Aut beatae vel ex quae magnam alias corrupti aliquam placeat.</span>  
      </div>
    </div>
  </div>
</template>
<script >
export default {
  mounted() {
    console.log(`chatMessage`)
    for (let index = 0; index < 10; index++) {
      const msg = {
        msg:"lorem iasfa lslalf salfaslf ",
        isAuthor: (index % 2 === 0),
      }
      this.msgs.push(msg)
    }
  },
  data(){
    return{
      msgs:[]
    }
  }
}
</script>
<style scoped>
.message::-webkit-scrollbar {
  display: none;
}

</style>
  