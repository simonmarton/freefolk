<template>
  <div id="app">
    <h2>Who dies next in GoT?</h2>
    <div class="character-list">
      <Character
        v-for="({ id, name, avatar, isAlive }) in characters"
        v-bind:key="id"
        v-bind:name="name"
        v-bind:avatar="avatar"
        v-bind:isAlive="isAlive"
        v-on:click.native="killCharacter(id)"
      />
    </div>
  </div>
</template>

<script>
import characters from "./characters-short.json";
import Character from "./components/Character.vue";

export default {
  name: "app",
  data: () => ({
    characters
  }),
  methods: {
    killCharacter: function(characterId) {
      const char = this.$data.characters.find(({ id }) => id === characterId);
      char.isAlive = false;
    }
  },
  components: {
    Character
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  background: darkgray;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  text-align: center;

  color: #2c3e50;
  margin-top: 60px;
}

.character-list {
  display: flex;
  flex-flow: wrap;
  justify-content: center;
}
</style>
