<template>
  <div id="app">

  </div>
</template>

<script>
import { eventBus } from './main.js';
import CharacterDetail from './components/CharacterDetail.vue';

export default {
  name: 'app',
  data(){
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  mounted(){
    fetch('http://hp-api.herokuapp.com/api/characters')
    .then(res => res.json())
    .then(characters => this.characters = characters)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })
  },
  components: {
    "character": Character
  }
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
