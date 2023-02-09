<template>
<div>
    <ul>
        <li 
        v-for="food, index in foods"
        :key="`${food-index}`">
        {{ food }} </li>
    </ul>
</div>
</template>

<script>
export default {
    props: { 
        foods: { type: Array, default: () => [] }
    }
}
</script>