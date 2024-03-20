<script setup>
import { ref } from "vue";
import { useRoute } from "vue-router";

const foodSingle = ref(null);
const route = useRoute();


async function getFetchSingleFoods(idMeal) {
  const res = await fetch(
    `https://www.themealdb.com/api/json/v1/1/lookup.php?i=${idMeal}`
  );
  const data = await res.json();
  foodSingle.value = data.meals;
}

console.log(foodSingle);
getFetchSingleFoods(route.params.id);
</script>

<template>
    <div class="foodSingle" v-for="item in foodSingle" :key="item.idMeal">
      <div class="foodSingle__info"> 
        <h3 class="foodSingle__info-area">Area: {{ item.strArea }}</h3>
        <img class="foodSingle__info-img" :src="item.strMealThumb" alt="" />
        <h2 class="foodSingle__info-title">{{ item.strMeal }}</h2>
      </div>
      <div class="foodSingle__ingredients">
        <h3 class="foodSingle__ingredients-title">Ingredients:</h3>
        <div class="foodSingle__ingredients-info" v-for="number in 20" :key="number">
          <p class="foodSingle__ingredients-txt">{{ item["strIngredient" + number] }}</p>
          <p class="foodSingle__ingredients-text">{{ item["strMeasure" + number] }}</p>
          <br>
          
        </div>
      </div>
      <div class="foodSingle__video">
        <video :src="item.strYoutube"></video>
      </div>
    </div>
</template>
