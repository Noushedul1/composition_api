<template>
  <div class="home">
    <p ref="p">{{name}} is {{age}} years old</p>
    <button @click="clickhandle()">click me</button>
  </div>
</template>

<script>
import {ref} from 'vue';
export default {
  name: 'Home',
  setup(){
    console.log('setup');
    const p = ref(null);
    const name = ref('akib');
    const age = ref(25);
    const clickhandle = () =>{
      // console.log(p, p.value);
      // p.value.classList.add('noushed');
      // p.value.textContent= 'hello noushedul islam';
      name.value = 'noushedul';
      age.value = 26;
    }
    return {name, age, clickhandle, p}
  }
}
</script>
