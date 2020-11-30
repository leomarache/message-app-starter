<template>
  <div class="message" @click="markAsRead()">
    <div class="sender-name"> {{ message.sender.name }}</div>
    <div class="sender-photo"><img :src="message.sender.profileImage" alt="Profile Picture"/></div>
    <div class="text-truncate">
      <div v-if="!message.read">
        <h5>{{ message.content }}</h5>
      </div>
      <div v-else>
        {{ message.content }}
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "Message",
  props: {
    message: Object,

  },
  methods: {
    markAsRead() {
      this.$emit("mark-as-read", true)
      //this.$emit("mark-as-read", !this.message.read);
      console.log("le bouton marche")
    }
  }
}
</script>

<style scoped>
.message {
  border-radius: 10px;
  color: black;
  border: 0.2px solid darkgrey;
}

.message:hover {
  background-color: darkgrey;

}

.sender-photo > img {
  height: 85px;
  width: 90px;
  border-radius: 50%;
}
</style>
