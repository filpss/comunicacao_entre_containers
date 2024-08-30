<script setup>
  import axios from 'axios';
  import {ref} from 'vue';

  const mensagem = ref()
  axios.get('mensagem').then((response)=>{
    // mensagem.value = response.data;
    console.log(response.data.message);
  }).catch((error) => {
    window.alert('Erro ao fazer requisição: ' + error);
  });

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  </header>
  <main>
    <h1>Resposta API</h1>
    <div class="resposta">
      <p>Mensagem: </p>
<!--      <pre>{{ mensagem.message }}</pre>-->
    </div>
  </main>
</template>

<style scoped>
  .resposta {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  pre {
    color: #3fb883;
    font-size: 18px;
  }
  p {
   font-size: 18px;
  }
</style>
