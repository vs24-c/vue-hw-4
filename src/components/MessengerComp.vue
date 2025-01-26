<template>
  <div>
    <h1>Messenger</h1>
    <ul class="read-mess">
      <li v-for="message in messages" :key="message.id" class="box__message">
        <strong>{{ message.sender }}:</strong> {{ message.content }}
        <button @click="onLike(message.id)">like</button>
        <button @click="onDis(message.id)">dislike</button>
        <span :class="message.status">{{ message.counter }}</span>
        <!-- <span>Likes: {{ message.likes }}</span>
        <span>Dislikes: {{ message.dislikes }}</span> -->
      </li>
    </ul>
  </div>
  <div class="write-mess">
    <input
      ref="newMessage"
      type="text"
      v-model="newMessage"
      placeholder="Type your message..."
    />
    <button @click="onSend">Send</button>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'MessengerComp',
  data() {
    return {
      messages: [],
      newMessage: '',
    };
  },
  methods: {
    onSend() {
      if (this.newMessage.trim()) {
        this.messages.push({
          sender: 'User',
          id: uuidv4(),
          content: this.newMessage,
          counter: 0,
          // likes: 0,
          // dislikes: 0,
          status: 'neutral',
        });
        this.newMessage = '';
        this.$refs.newMessage.focus();
      }
    },
    onLike(messageId) {
      const message = this.messages.find((msg) => msg.id === messageId);
      if (message) {
        message.counter++;
        message.status = 'likes';
      }
    },
    onDis(messageId) {
      const message = this.messages.find((msg) => msg.id === messageId);
      if (message) {
        message.counter--;
        message.status = 'dislikes';
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.read-mess {
  display: flex;
  flex-direction: column;
  gap: 15px;
}
.box__message {
  list-style: none;
  display: flex;
  gap: 7px;
  & button {
    background-color: orchid;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
}
.neutral {
  color: transparent;
}
.likes {
  color: green;
}
.dislikes {
  color: red;
}
</style>
