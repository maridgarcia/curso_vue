<template>
  <div id="app">
    <input type="text" v-model="name">
    <h1 :style="{ textDecoration: decoration }">Hello {{ name }}</h1>
  </div>
</template>

<script>
export default {
  data: () => ({
    name: '',
    decoration: 'underline'
  })
}

</script>

<style>

</style>
