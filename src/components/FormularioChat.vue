<template>
  <form style="width: 400px;" class="p-2" @submit.prevent="emitForm">
    <img :src="srcImg" style="width: 80%;">
    <h3>{{ name }}</h3>
    <label for="">
      <input v-model="color" type="color">
    </label>
    <label for="">
      <textarea v-model="msj" maxlength="150"></textarea>
    </label>
    <button type="submit" class="p-2 w-75">Enviar</button>
  </form>
</template>

<script>
export default {
  name: 'FormularioChat',
  data() {
    
    return {
      msj: 'text for example',
      color: this.colorProp,
    }
  },
  props: {
    srcImg: String,
    name: String,
    colorProp:{
      type:String,
      default:'#ff0000'
    }
  },
  methods: {
    emitForm() {
      this.$emit('form-sent', { name: this.name, msj: this.msj, color: this.color })
    }
  }
};
</script>

<style scoped>
label {
  display: block;
}

label>input {
  width: 90%;
}

textarea {
  width: 90%;
}
</style>
