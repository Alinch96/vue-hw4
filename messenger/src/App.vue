<template>
  <div>
    <ul v-if="messages.length > 0">
      <message-item
        v-for="message in messages"
        :key="message.id"
        :message="message"
        @like="onLike"
        @dislike="onDislike"
      />
    </ul>
    <message-area @add="addMessage" />
  </div>
</template>

<script>
import MessageArea from "./components/MessageArea.vue";
import MessageItem from "./components/MessageItem.vue";

export default {
  name: "App",
  components: { MessageArea, MessageItem },

  data() {
    return {
      messages: [],
    };
  },
  methods: {
    addMessage(message) {
      this.messages.push(message);
    },
    onLike(id) {
      const message = this.messages.find((message) => message.id === id);
      message.likes++;
    },
    onDislike(id) {
      const message = this.messages.find((message) => message.id === id);
      message.likes--;
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
