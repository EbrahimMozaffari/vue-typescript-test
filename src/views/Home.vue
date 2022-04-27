<template>
  <div class="home">
   hello ebrahim
   <p>{{name}}</p>
   <button @click="changeName('gholi')">change name</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default defineComponent({
  name: 'Home',
  components: {

  },
  data(){
    return {
      name:'link',
      age : 25 as number | string,
      
    }
  },
  methods:{
    changeName(name:string){
      this.name = name;
    }
  }
});
</script>
