<template>
  <div class="home">
    <p v-for="name in names" :key="name">
      {{name}}
    </p>
  </div>
</template>

<script>
import {computed, ref} from 'vue';
export default {
  name: 'Home',
  setup(){
    const names = ref(['akib','aki','shaki','mohima','arman']);
    return {names}
  }
}
</script>
