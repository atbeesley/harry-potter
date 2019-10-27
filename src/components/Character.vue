<template lang="html">
  <div class="character-list" v-if="characters.length">
    <character-detail
    v-for="(character, index) in characters"
    :character="character"
    :key="index"
    >
  </character-detail>

  </div>

</template>

<script>
import CharacterDetail from "@/components/CharacterDetail";
export default {
  name: "character-detail",
  props: ["characters"],
  components: {
    "character-detail": CharacterDetail
  }
};
</script>

<style lang="css" scoped>
</style>
