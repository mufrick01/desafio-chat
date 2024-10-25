<template>
        <div :style="{backgroundColor:message.color}" :class="{'ms-auto':this.message.user=='userB'}" class="w-75 m-2">
            <p class="fw-bold m-2">{{ message.name }}</p>
            <p class="m-2" >{{ message.msj }}</p>
        </div>
</template>

<script>
export default {
  name: 'ChatMessage',
  props:{
      message:Object
  },
};
</script>

<style scoped>
/* Estilos aquí */
</style>
