<template>
  <section class="d-flex container" style="height: 100vh;">
    <FormularioChat colorDefault="#f00" name="Goku" srcImg="https://media.gq.com.mx/photos/5eb5954e51cd5e1b340e8b67/16:9/w_2560%2Cc_limit/dia-de-goku.png" @form-sent="formHandlerUserA"/>
      <div class="bg-info flex-grow-1">
        <ChatComponent :messages="msjList"/>
      </div>
    <FormularioChat colorProp="#0000ff" name="Vegeta" srcImg="https://i.blogs.es/b60b7d/vegeta/1366_2000.jpeg" @form-sent="formHandlerUserB"/>
  </section>
</template>

<script>
import ChatComponent from './components/ChatComponent.vue';
import FormularioChat from './components/FormularioChat.vue';


export default {
  name: 'App',
  components: {
    FormularioChat,
    ChatComponent,
  },
  data(){
    return{
      msjList:[],

      userNameLeft:'',
      userImgLeft:'',
      
      userNameRight:'',
      userImgRight:'',
    }
  },
  created(){
    this.hitApi();
  },
  methods:{
    formHandlerUserA(data){
      this.msjList.push({user:'userA',...data});      
    },
    formHandlerUserB(data){
      this.msjList.push({user:'userB',...data});      
    },
    async hitApi(){
      const resp = await fetch('');
      const data = await resp.json();
      console.log(data);

    }
  },
  
}
</script>

<style>
#app {
}
</style>
