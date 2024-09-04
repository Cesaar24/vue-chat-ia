<template>
  <div class="h-32 w-full z-10  ">
    
    <div class="form mx-auto rounded-full w-3/4 h-20  relative ">
      <textarea v-model="text"
        wrap="hard"
        class="w-full h-full rounded-full bg-transparent content-center pl-6 pr-12 "
        :class="[!focus ? 'bg-neutral-800' : 'bg-neutral-700']" 
        placeholder="Describe yourself here..."
        @focus="focusForm" @focusout="focusForm"
      >
        
      </textarea>
      <div 
        class="icon absolute top-0 bottom-0 m-auto  w-8 h-8 content-center  overflow-hidden"
        :class="[focus && text.length != 0 ? 'right-3 cursor-pointer' : 'opacity-0 -right-10 ']"
      >
        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" class="fill-cyan-500 my-auto" viewBox="0 0 24 24"><path d="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z"/></svg>
      </div>
    </div>
    
    <!-- <div 
      class="form mx-auto rounded-full flex w-3/4 h-20 text-xs md:text-base xl:text-lg sm:text-sm text-start"
      :class="[!focus ? 'bg-neutral-800' : 'bg-neutral-700']"
      contenteditable="true"
      ref="divForm"
      @keydown="inputForm($event)"
      @focus="focusForm" @focusout="focusForm"
    > 
      <div 
        class="ml-4 text content-center text-slate-100" 
        :class="{'placeText': !text.length }"
        placeholder="Enter text here..." 
        
      >
        <br>
      </div>
      <div class=" " :class="[!focus ? 'opacity-0' : 'opacity-100']">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" class="fill-cyan-500 " viewBox="0 0 24 24"><path d="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z"/></svg>
      </div>
    </div> -->
    
  </div>
</template>
<script >
export default {
  mounted() {
    console.log(`chatForm`)
    
  },
  data(){
    return{
      focus:false,
      text:""
    }
  },
  methods:{
    focusForm(){
      this.focus = !this.focus
    },
    inputForm(event){
      
      console.log(event)
      if (event.key === 'Backspace') {
        this.text = this.text.slice(0, -1)
        // Si estamos al inicio de un elemento, evitamos que se elimine
        const selection = window.getSelection();
        const range = selection.getRangeAt(0);
        if (range.startOffset === 0) {
          event.preventDefault();
        }
      }else{
        this.text += event.key
      }

    }
  }
}
</script>
<style scoped>
.form{
  background: #1e1f20;
  
}
textarea {
  resize: none;
  outline: none;
  word-wrap: break-word;
  /* width: 95%; */
}
textarea::-webkit-scrollbar {
  display: none;
 
}
.icon{
  transition: all 0.3s;

}


.placeText::before{
  content: attr(placeholder);
  pointer-events: none;
  cursor: cell;
  position: absolute;
  z-index: 0;
}

</style>
  