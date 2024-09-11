<template>
  <div id="app">
    <NavBar />
    <div class="container">
      <div class="row">
        <h1>Batsmen</h1>
        <div class="col-md-4" v-for="player in batsmen" :key="player.name">
          <PlayerCard :player="player" />
        </div>
      </div>
      <div class="row">
        <h1>Bowlers</h1>
        <div class="col-md-4" v-for="player in bowlers" :key="player.name">
          <PlayerCard :player="player" />
        </div>
      </div>
      <div class="row">
        <h1>All-Rounders</h1>
        <div class="col-md-4" v-for="player in allRounders" :key="player.name">
          <PlayerCard :player="player" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from './components/Navbar.vue'
import PlayerCard from './components/PlayerCard.vue'
import players from './players.json'

export default {
  components: {
    NavBar,
    PlayerCard
  },
  data() {
    return {
      players: players.originalPlayers
    }
  },
  computed: {
    batsmen() {
      return this.players.filter(player => player.role === 2);
    },
    bowlers() {
      return this.players.filter(player => player.role === 4);
    },
    allRounders() {
      return this.players.filter(player => player.role === 3);
    }
  }
}
</script>

<style>
/* From Uiverse.io by HarryHeywood04 */ 
#app {
  width: 100%;
  height: 100%;
  background-color: #111111;
  background-image: linear-gradient(
    32deg,
    rgba(8, 8, 8, 0.74) 30px,
    transparent
  );
  background-size: 60px 60px;
  background-position: -5px -5px;
}

</style>