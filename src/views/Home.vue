<template>
  <div class="home">
    <p>{{p.name}} is {{p.age}} years old</p>
    <button @click="clickhandle()">click me</button>
  </div>
</template>

<script>
import {ref,reactive} from 'vue';
export default {
  name: 'Home',
  setup(){
    console.log('setup');
    const p = reactive({name: 'akib',age: 25});
    const clickhandle = () =>{
      // console.log(p, p.value);
      // p.value.classList.add('noushed');
      // p.value.textContent= 'hello noushedul islam';
      p.name = 'noushedul';
      p.age = 26;
    }
    return {clickhandle, p}
  }
}
</script>
