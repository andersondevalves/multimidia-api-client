<template>
    <div class="card">
        <img :src="personage.image" width="50" height="70"> 
            <p class="card-title">{{ personage.name }}</p>
            <ul class="card-description">
              <li>Força: {{ personage.ki }}</li>
              <li>Maximo de Força: {{ personage.maxKi }}</li>
              <li>raça: {{ personage.race }}</li>
            </ul>
          </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        personage:{
            type: Object,
            required: true
        }
    },
      
 }
</script>

<style>

</style>