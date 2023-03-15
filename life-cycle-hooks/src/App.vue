<template>
    <h1>Life cycle hooks</h1>
</template>

<script>
// composition api
// import { onMounted } from 'vue';

// export default {
//   setup () {
//     onMounted(() => {
//       console.log("mounted composition api")
//     })
//   }
// }


export default {
  mounted () {
    console.log("mounted")
  }
}

// https://vuejs.org/api/composition-api-lifecycle.html#onmounted
</script>
