<template>
  <div class="menu">
    <h1> Ici, mon beau menu {{unreadMessages}}</h1>
  </div>
</template>

<script>
export default {
  name: "Menu",
  props: {
    unreadMessages: Number,
  }
}
</script>

<style scoped>
.menu {
  border-style: dotted;
  color: black;
}
</style>
