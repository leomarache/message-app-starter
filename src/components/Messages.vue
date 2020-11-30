<template>
  <div class="messages">
    <h1>Messages</h1>
    <Message role="button" v-on:mark-as-read="markAsRead(currentMessage, $event)" v-for="currentMessage in messages"
             :key="currentMessage.id" :message="currentMessage"/>

  </div>
</template>

<script>
import Message from "./Message";
import {messagesMock} from "@/mocks/messages.mock";


export default {
  name: "Messages",
  components: {Message},
  created() {
    this.sortMessagesByDate();
    this.countUnreadMessages();
  },
  data() {
    return {
      messages: messagesMock,

    }
  },
  methods: {
    markAsRead(message, event) {
      message.read = event;
      this.countUnreadMessages();
    },
    sortMessagesByDate(){
      this.messages.sort((m1, m2) => new Date(m2.date) - new Date(m1.date)); // Ordre chronologique
    },
    countUnreadMessages() {
      this.unreadMessages = this.messages.filter((message) => !message.read).length;
      console.log(this.unreadMessages)
      this.$emit("count-unread-messages", this.unreadMessages)
    }
  }


}
</script>

<style scoped>
.messages {
  border-style: solid;
  color: blue;

}

.messages:hover {

}
</style>
