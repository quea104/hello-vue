<script setup>
  import {ref} from 'vue';
  import axios from 'axios';
  import Header from './components/Header.vue';
  import Content from './components/Content.vue';
  import Footer from './components/Footer.vue';

  const message = ref('환영합니다. Vue 몰입니다.');
  const list = ref([{title:'아이폰'},{title:'갤럭시'},{title:'아이패드'}]);
  const todos = ref();
  const copyright = ref('Copyright 2023 by SEO');

  // Vue 에서는 function 으로 선언 권장
  function buttonClicked() {
    console.log('button clicked');
    copyright.value = 'Button Clicked';
    getTodosFromServer();
  }

  function getTodosFromServer() {
    axios.get('https://jsonplaceholder.typicode.com/todos')
      .then(res => {
        console.log(res.data);
        todosTitle.value = "할일";
        todos.value = res.data;
      })
      .catch(error => {
        console.loog(error);
      });
  }
</script>

<template>
  <Header :message="message"/>

  <button @click="buttonClicked">Push Button</button>

  <Content :list="list"/>
  <Content :list="todos"/>

  <Footer :copyright="copyright"/>
</template>

<style scoped>

</style>