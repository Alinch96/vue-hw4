<template>
    <div class="message-area">
       <input type="text" v-model="messageText" />
        <button :disabled="!messageText" @click="addMessage">Send</button>
    </div>
</template>

<script>
export default {
    name: 'MessageArea',
    data() {
        return {
            messageText: '',
        };
    },
    methods: {
        addMessage() {
            this.$emit('add', {
                id: new Date().getTime(), 
                text: this.messageText,
                likes: 0,
            });
            this.messageText = '';
        },
    },
};
</script>

<style scoped>
.message-area {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.message-area input {
  width: 250px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
}

.message-area button {
  background-color: #007BFF;
  margin-left: 10px;
}

.message-area button:hover {
  background-color: #0056b3;
}
</style>