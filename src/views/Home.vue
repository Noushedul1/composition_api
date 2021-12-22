<template>
  <div class="home">
    <input type="text" v-model="search">
    <p>search term --- {{search}}</p>
    <p v-for="name in matchingNames" :key="name">
      {{name}}
    </p>
    <button @click="watchHandle()">stop watch</button>
  </div>
</template>

<script>
import {computed, ref, watch, watchEffect} from 'vue';
export default {
  name: 'Home',
  setup(){
    const search = ref();
    const names = ref(['akib','aki','shaki','mohima','arman']);
   const stopwatch = watch(search, ()=>{
     console.log('watching search ...')
   })
   const stopeffect = watchEffect(()=>{
     console.log('i am watching.......................', search.value)
   })
   const watchHandle = ()=>{
     stopwatch()
     stopeffect()
   }
    const matchingNames = computed(()=>{
      return names.value.filter((name)=>name.includes(search.value));
    });
    return {names,search,matchingNames,watchHandle}
  }
}
</script>
