<script setup>

const props = defineProps({
  info: {
    type: Object,
    required: true,
  }
})

</script>
<template>
    <RouterLink 
    :to="'/foods-single/' + info.idMeal" 
    class="foods__card"
    >
      <img class="foods__card-img" :src="info.strMealThumb" alt="">
      <h2 class="foods__card-title">{{ info.strMeal }}</h2>
    </RouterLink>
</template>

