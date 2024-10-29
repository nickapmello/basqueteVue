<template>
  <div class="list-container">
    <h1>Lista de Jogadores de Basquete</h1>
    <div class="form-container">
      <input v-model="newPlayer.name" placeholder="Nome do Jogador">
      <input v-model="newPlayer.position" placeholder="Posição">
      <input v-model="newPlayer.team" placeholder="Time">
      <button class="add-button" @click="addPlayer">Cadastrar</button>
    </div>
    <div v-if="basketballPlayers.length" class="player-list">
      <ul>
        <li v-for="(player, index) in basketballPlayers" :key="player.id">
          {{ player.name }} - {{ player.position }} - {{ player.team }}
          <button class="remove-button" @click="removePlayer(index)">Remover</button>
        </li>
      </ul>
    </div>
    <div v-else>
      <p>Nenhum jogador cadastrado.</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newPlayer: {
        name: '',
        position: '',
        team: ''
      },
      basketballPlayers: []
    };
  },
  methods: {
    addPlayer() {
      if (this.newPlayer.name && this.newPlayer.position && this.newPlayer.team) {
        this.basketballPlayers.push({ ...this.newPlayer, id: Date.now() });
        this.newPlayer = { name: '', position: '', team: '' };
      } else {
        alert("Por favor, preencha todos os campos.");
      }
    },
    removePlayer(index) {
      this.basketballPlayers.splice(index, 1);
    }
  }
}
</script>

<style scoped>
.list-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-container input, .form-container button {
  padding: 15px;
  margin: 10px 0;
  border: none;
  border-radius: 5px;
  width: 100%;
}

.add-button {
  background-color: #4CAF50;
  color: white;
  cursor: pointer;
}

.add-button:hover {
  background-color: #367c39;
}

.player-list ul {
  padding: 0;
}

.player-list li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  background-color: #333;
  color: white;
  border-radius: 5px;
  margin-top: 10px;
}

.remove-button {
  padding: 5px 10px;
  background-color: #e53935;
  border-radius: 5px;
  color: white;
  cursor: pointer;
}

.remove-button:hover {
  background-color: #b71c1c;
}
</style>
