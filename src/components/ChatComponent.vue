<template>
  <div class="w-100 d-flex flex-column">
    <h1>Lista de mensajes</h1>
    
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
