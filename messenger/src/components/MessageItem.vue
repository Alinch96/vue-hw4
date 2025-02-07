<template>
  <div class="message-item">
    <span class="message-text">{{ message.text }}</span>
    <button @click="onLike">👍</button>
    <button :disabled="message.likes === 0" @click="onDislike">👎</button>
    <span>{{ message.likes }}</span>
  </div>
</template>

<script>
export default {
  name: "MessageItem",
  props: {
    message: Object,
  },
  methods: {
    onLike() {
      this.$emit("like", this.message.id);
    },
    onDislike() {
      this.$emit("dislike", this.message.id);
    },
  },
};
</script>

<style scoped>
.message-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #f9f9f9;
  margin: 10px 0;
  padding-right: 64px;
}

.message-text {
  flex-grow: 1;
  font-size: 16px;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 10px;
}

button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 8px 12px;
  margin: 0 5px;
  cursor: pointer;
  border-radius: 4px;
  font-size: 14px;
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}

button:hover:not(:disabled) {
  background-color: #45a049;
}
</style>
