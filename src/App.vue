<template>
  <section class="d-flex container" style="height: 100vh;">
    <FormularioChat colorDefault="#f00" :name="userNameLeft" :srcImg="userImgLeft" @form-sent="formHandlerUserA"/>
      <div class="bg-info flex-grow-1">
        <ChatComponent :messages="msjList"/>
      </div>
    <FormularioChat colorProp="#0000ff" :name="userNameRight" :srcImg="userImgRight" @form-sent="formHandlerUserB"/>
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
      const resp = await fetch('https://randomuser.me/api/?results=2');
      const data = await resp.json();
      const usersList = data.results;
      
      
      // console.log(usersList);
      // console.log(usersList[0].name.title);
      // console.log(usersList[0].picture.large);


      this.userNameLeft = `${usersList[0].name.title} ${usersList[0].name.first}`;
      this.userImgLeft = `${usersList[0].picture.large}`
      
      this.userNameRight = `${usersList[1].name.title} ${usersList[1].name.first}`;
      this.userImgRight = `${usersList[1].picture.large}`

    }
  },
  
}
</script>

<style>
#app {
}
</style>
