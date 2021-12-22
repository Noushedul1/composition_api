<template>
  <div class="home">
    <p>{{p}}</p>
  </div>
</template>

<script>
import {computed, ref} from 'vue';
export default {
  name: 'Home',
  setup(){
    const p = computed(()=>{
      return 'noushed';
    });
    return {p}
  }
}
</script>
