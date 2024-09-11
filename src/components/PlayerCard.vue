<template>
    <div class="card-container">
      <div class="card" v-for="player in players" :key="player.name">
        <img :src="'https://via.placeholder.com/150'" class="card-img-top" alt="Player Image" />
        <div class="card-body">
          <h5 class="card-title">{{ player.name }}</h5>
          <p class="card-text">Matches: {{ player.matches }}</p>
          <p class="card-text">Runs: {{ player.runs }}</p>
          <p class="card-text">50s/100s: {{ player['50s'] }}/{{ player['100s'] }}</p>
          <p class="card-text">Highest Score: {{ player.highest_score }}</p>
          <p class="card-text">Team: {{ player.team_name }}</p>
          <p class="card-text">Best Bowling Figures: {{ player.best_bowling_figures }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import playersData from '../players.json'; // Adjust the path based on your project structure
  
  export default {
    data() {
      return {
        players: playersData.originalPlayers // Adjust based on your JSON structure
      };
    }
  }
  </script>
  
  <style scoped>
  .card-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 cards per row */
    gap: 30px; /* Space between cards */
    margin: 20px auto; /* Center horizontally */
    max-width: 1200px; /* Limit the maximum width of the container */
    padding: 0 20px; /* Add some horizontal padding */
  }
  
  .card {
    display: flex;
    flex-direction: column;
    border-radius: 10px;
    overflow: hidden;
    transition: box-shadow 0.3s ease-in-out, transform 0.3s ease-in-out;
    box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.2); /* Enhanced shadow for 3D effect */
    border: 4px solid green; /* Green border */
  }
  
  .card:hover {
    box-shadow: 0px 12px 24px rgba(0, 0, 0, 0.3); /* More pronounced shadow on hover */
    transform: translateY(-8px); /* More pronounced lift on hover */
  }
  
  .card-img-top {
    height: 150px;
    object-fit: cover;
  }
  
  .card-body {
    padding: 15px;
    background-color: #000000;
    color: green;
  }
  
  .card-title {
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 10px;
  }
  
  .card-text {
    font-size: 14px;
    color: #ffffff;
  }
  
  @media (max-width: 768px) {
    .card-container {
      grid-template-columns: repeat(2, 1fr); /* 2 cards per row on tablet */
    }
  }
  
  @media (max-width: 480px) {
    .card-container {
      grid-template-columns: 1fr; /* 1 card per row on mobile */
    }
  }
  </style>
  