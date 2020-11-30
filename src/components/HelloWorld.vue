<template>
  <div class="hello">
    <div>
      <h1>{{msg}}</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  margin: 40px 0 0;
  border: dotted aqua;
  color: aqua;
}
</style>
