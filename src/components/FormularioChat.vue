<template>
  <form style="width: 400px;" class="p-3 mt-5" @submit.prevent="emitForm">
    <img :src="srcImg" style="width: 100%; border-radius: 50%;">
    <h3>{{ name }}</h3>
    <label for="">
      <input v-model="color" type="color">
    </label>
    <label for="">
      <textarea v-model="msj" maxlength="150" style="height: 150px;"></textarea>
    </label>
    <button type="submit" class="p-2 w-100 btn btn-primary borde">Enviar</button>
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
      const now = new Date;
      const hours = now.getHours();
      const minutes = now.getMinutes();
      const time = `${hours}:${minutes}`;
      this.$emit('form-sent', { name: this.name, msj: this.msj, color: this.color, time })
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

.borde{
border-radius: 10px;
}
</style>
