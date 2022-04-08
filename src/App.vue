<template>
  <div id="app">
    <div class="input">
    <label for="number">Input Number: </label>
    <input type="number" v-model="limit" />

    </div>
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
.input{
  margin-left: auto;
  margin-right: auto;
}
input{
  height: 40px;
  width: 210px;
  font-size: 2rem;
  margin-bottom: 80px;
}
label{
  font-family: sans-serif;
  font-size: 2rem;
}
</style>
