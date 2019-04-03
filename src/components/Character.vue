<template>
  <div class="character" v-bind:class="{ dead: !isAlive }">
    <img :src="avatar" :alt="name" class="avatar">
    <span class="name">{{name}}</span>
  </div>
</template>

<script>
export default {
  name: "Character",
  props: {
    avatar: String,
    name: String,
    isAlive: Boolean
  }
};
</script>

<style>
.character {
  display: flex;
  align-items: center;
  width: 400px;
  padding: 10px;
  margin: 10px;
  border-radius: 50px;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
  background: white;
  cursor: pointer;
  transition: opacity 0.5s;
}

.avatar {
  width: 80px;
  height: 80px;
  object-fit: cover;
  object-position: top;
  border-radius: 50%;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
}

.name {
  font-size: 24px;
  margin-left: 1rem;
}

.character.dead {
  opacity: 0.4;
  cursor: default;
}

.character.dead .name {
  text-decoration: line-through;
}
</style>

