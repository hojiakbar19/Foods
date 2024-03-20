<script setup>
import { RouterLink } from 'vue-router';



</script>
<template>
   <header class="header">
    <nav class="header__nav">
        <div class="container">
            <RouterLink to="/" class="header__nav-link"><img src="https://www.themealdb.com/images/logo-small.png" alt=""></RouterLink>
            
            <div class="header__info">
                <RouterLink to="/"  class="header__info-btn">Home</RouterLink>
                <button  class="header__info-btn">API</button>
                
            </div>
        </div>
    </nav>
   </header>
</template>


<style></style>