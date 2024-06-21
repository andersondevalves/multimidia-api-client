<template>
    <div class="card">
        <img :src="bet.image" width="50" height="70"> 
            <p class="card-title">{{ bet.nome }}</p>
            <ul class="card-description">
              <li>Força: {{ bet.email }}</li>
              <li>Maximo de Força: {{ bet.idade }}</li>
              <li>raça: {{ bet.time }}</li>
            </ul>
          </div>
</template>

<script>
export default {
    name: 'Cardlocal',
    props: {
        bet:{
            type: Object,
            required: true
        }
    },
      
 }
</script>

<style>

</style>