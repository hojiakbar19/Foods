<script setup>
import { ref } from "vue"
import Card from "../components/card/Card.vue";

const foods = ref(null)
async function router() {
    const res = await fetch("https://www.themealdb.com/api/json/v1/1/search.php?f=a")
    const data = await res.json()
    foods.value = data.meals
}

router()
</script>
<template>
    <div class="foods">
        <div class="container">
            <h1 class="foods__title">Foods</h1>
            <div class="foods__cards" >
                <Card v-for="item in foods" :key="item.idMeal" :info="item" />
            </div>
            
        </div>
    </div>
    
</template>


