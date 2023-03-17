<template>
  <div>
    <h3>Games List</h3>
    <div v-for="game in games" :key="game.id">
      <p>{{ game.name }}</p>
      <p>{{ game.price }}</p>
      <p>{{ game.genre }}</p>
      <img :src="game.image" alt="game image" />
    </div>
  </div>
</template>

<script>
import axios from "axios"
export default {
  name: "GamesList",
  data() {
    return {
      games: [],
    }
  },
  created() {
    let url =
      "https://my-json-server.typicode.com/nelson2411/typescript-redux-wishlist-project/videogames/"
    axios.get(url).then((response) => {
      this.games = response.data
    })
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
