<template>
  <div>
    <div class="container">
      <div v-for="personage in personagens" :key="personage.id">
        <card :personage="personage">
  
        </card>
      </div>
    </div>
  </div>

</template>

<script>
 import Card from '../components/Card.vue'

const API_URL = `https://dragonball-api.com/api/characters`

export default {
  data: () => ({
    personagens: []

  }),
  methods: {
    async getPersonagens () {
      const response = await fetch(API_URL)
      const data = await response.json()
      
      this.personagens = data.items
    }
  },
  created() {
    this.getPersonagens()
  },
  components: {
    Card
  }
}
</script>
<style>
body {
  background-color: rgb(212, 109, 71);
}

.title {
  color: #FFE807;
}

.type {
  color: white;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  text-align: center;
}


.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 100%;
}

.card {
  background-color: rgb(69, 104, 180);
  border-radius: 10px;
  margin: 20px;
  height: 250px;
  width: 250px;
  text-align: center;
  align-content: center;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

.card-title {
  color: #FFE807;
  font-size: 20px;
  font-weight: bold;
  text-shadow: 1px 1px 5px black;
}

.card-description {
  font-size: 14px;
  text-align: start;
  padding-left: 50px;
}
</style>