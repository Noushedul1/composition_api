<template>
  <div class="home">
    <input type="text" v-model="search">
    <p>search term --- {{search}}</p>
    <p v-for="name in matchingNames" :key="name">
      {{name}}
    </p>
  </div>
</template>

<script>
import {computed, ref, watch, watchEffect} from 'vue';
export default {
  name: 'Home',
  setup(){
    const search = ref();
    const names = ref(['akib','aki','shaki','mohima','arman']);
   watch(search, ()=>{
     console.log('watching search ...')
   })
   watchEffect(()=>{
     console.log('i am watching.......................', search.value)
   })
    const matchingNames = computed(()=>{
      return names.value.filter((name)=>name.includes(search.value));
    });
    return {names,search,matchingNames}
  }
}
</script>
