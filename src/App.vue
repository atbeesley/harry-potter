<template>
  <div id="app">

  </div>
</template>

<script>
import { eventBus } from './main.js';
import CharacterListList from './components/CharacterList.vue';

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
    .then(munros => this.characters = characters)

    eventBus.$on('character-selected', (munro) => {
      console.log('within $on', character);
    })
  },
  components: {
    "characters-list": CharacterList
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
