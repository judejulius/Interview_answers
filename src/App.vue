<template>
  <div id="app">
    <label for="number">Input Number: </label>
    <input type="number" v-model="limit" />
    <Numbers/>
  </div>
</template>

<script>
import Numbers from '@/components/Numbers';

export default {
  name: 'App',
  components: {Numbers},
  data()
  {
    return {
      limit: 100
    }
  }
}
</script>

<style scoped>
input{
  height: 20px;
  width: 210px;
  font-size: 1rem;
}
label{
  font-family: sans-serif;
}
</style>
