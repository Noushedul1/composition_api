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
import {computed, ref} from 'vue';
export default {
  name: 'Home',
  setup(){
    const search = ref();
    const names = ref(['akib','aki','shaki','mohima','arman']);
    const matchingNames = computed(()=>{
      return names.value.filter((name)=>name.includes(search.value));
    });
    return {names,search,matchingNames}
  }
}
</script>
