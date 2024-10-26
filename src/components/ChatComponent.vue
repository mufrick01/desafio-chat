<template>
  <div class="w-100 bg-dark  d-flex flex-column">
    <h1 class="text-center mb-5 mt-3">Lista de mensajes</h1>
    <ChatMessage v-for="(message, index) in messages" :message="message" :key="index"/>
  </div>
</template>

<script>
import ChatMessage from './ChatMessage.vue';

export default {
  name: 'ChatComponent',
  components:{
    ChatMessage
  },
  data() {
    return {
      // Datos aquí
    };
  },
  props:{
      messages:Array
  }
};
</script>

<style scoped>
/* Estilos aquí */
</style>
