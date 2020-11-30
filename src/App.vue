<template>
  <div class="app">
    <h1>L'app</h1>
    <HelloWorld :msg="'Hello world'"/>
    <Messages/>
    <Menu :count-unread-messages="numberOfUnreadMessages"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Messages from "@/components/Messages";
import Menu from "@/components/Menu";


export default {
  name: "App",
  components: {
    HelloWorld,
    Messages,
    Menu,
  },
  data() {
      return {
        numberOfUnreadMessages: 0
      }

  },
  methods: {
    countUnreadMessages(message,event) {
      message.read = event;
      console.log(this.numberOfUnreadMessages)
    }
  }
};
</script>

<style>
html, body {
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: crimson;
  border-style: solid;

}
</style>
