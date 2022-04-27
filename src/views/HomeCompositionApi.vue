<template>
  <div class="home">
    hello ebrahim
    <p>{{ name }}</p>
    <!-- <button @click="changeName('gholi')">order by title</button> -->
    <button @click="handleClick('title')">order by title</button>
    <button @click="handleClick('salary')">order by salary</button>
    <button @click="handleClick('location')">order by location</button>
    <hr />
    <jobList :jobs="jobs" :order='order' />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Job from "../types/job";
import OrderTerm from "../types/orderTerm";
import jobList from "@/components/jobsList.vue";
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default defineComponent({
  name: "HomeCompositionApi",
  components: {
    jobList,
  },
  setup() {
    // const state = reactive({
    //   name:'Ebi',
    //   age:25 as string | number
    // })

    // return {...toRefs(state),changeName}
    const name = ref<string>("Ebiii");
    const age = ref<number | string>(25);
    // const changeName = (name:string) => {
    //   name.value = name;
    // };

    const jobs = ref<Job[]>([
      { title: "t1", location: "iran", salary: 15000, id: "1" },
      { title: "t2", location: "dgdfgdf", salary: 45645, id: "2" },
      { title: "t3", location: "irgfdgan", salary: 76575, id: "3" },
      { title: "t5", location: "gigfdgdran", salary: 15415, id: "4" },
      { title: "t6", location: "ggfdgiran", salary: 87464, id: "5" },
    ]);
const order = ref<OrderTerm>('title')

    const handleClick= (term: OrderTerm)=>{
          order.value = term;
    }
    return {
      name,
      age,
      // changeName,
      jobs,
      handleClick,
      order,
    };
  },
  // data(){
  //   return {
  //     name:'link',
  //     age : 25 as number | string,

  //   }
  // },
  // methods:{
  //   changeName(name:string){
  //     this.name = name;
  //   }
  // }
});
</script>
