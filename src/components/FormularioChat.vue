<template>
  <form style="width: 400px;" class="p-2" @submit.prevent="emitForm">
    <img :src="srcImg" style="width: 100%;">
    <h3>{{ name }}</h3>
    <label for="">
      <input v-model="color" type="color">
    </label>
    <label for="">
      <textarea v-model="msj" maxlength="150" style="height: 200px;"></textarea>
    </label>
    <button type="submit" class="p-2 w-100">Enviar</button>
  </form>
</template>

<script>
export default {
  name: 'FormularioChat',
  data() {
    
    return {
      msj: 'text to example',
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
  width: 100%;
}

textarea {
  width: 100%;
}
</style>
