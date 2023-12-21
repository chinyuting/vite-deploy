<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ data }}
    {{ text }}
  </div>
</template>

<script setup>
import {ref} from 'vue';
import axios from 'axios';

// export default {
  const data = ref({});
  const text = ref('');
  console.log(import.meta.env.VITE_PATH);
  const url = import.meta.env.VITE_PATH;
  text.value = import.meta.env.VITE_TEXT;
  axios.get(url)
    .then((res) => {
      data.value = res;
    });
// }
  
</script>
  
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
