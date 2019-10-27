<template lang="html">
  <div class="characterlistitem">
    <p>{{ character.name }}</p>
      <button v-on:click="displayInfo">More Info &rarr;</button>

  </div>

</template>

<script>
import { eventBus } from '@/main.js';

export default {
  name: "character-list-item",
  props: ["character"],
  methods: {
    displayInfo: function () {
      eventBus.$emit("character-selected", this.character);
    },
  }
};
</script>

<style lang="css" scoped>
</style>
