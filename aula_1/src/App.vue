<template>
<div>
  <input type="text" v-model="currentFood" @keyup.enter="handleClick">
  <button v-on:click="handleClick">
    add!
  </button>
  <food-list
    @my-event="handleClick"
    :foods="foods"
  />
</div>
</template>

<script>
import FoodList from './components/FoodList'

export default {
  components: { FoodList },
  data () {
    return {
      currentFood: "",
      foods: []
    }
  },
  methods: {
    handleClick() {
      this.foods.push(this.currentFood)
      this.currentFood = ""
    }
  }
}
</script>
