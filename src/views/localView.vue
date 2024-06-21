<template>
  <div>
    <div class="container">
      <div v-for="bet in bets" :key="bet.id">
        <card-local :bets="bets"></card-local>
  
      </div>
    </div>
  </div>

</template>

<script>
 import Cardlocal from '@/components/CardLocal.vue'

const API_URL = `http://localhost:3333/bets`

export default {
  data: () => ({
    bets: []

  }),
  methods: {
    async getbets () {
      const response = await fetch(API_URL)
      const data = await response.json()
      
      this.bets = data
    }
  },
  created() {
    this.getbets()
  },
  components: {
    Cardlocal
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