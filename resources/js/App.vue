

<template>
    <div id="app">
        <Loading />
        <NavBar />
        <Datatable />
    </div>
  </template>

  <script>
  import Loading  from './components/Loading.vue'
  import Datatable from './components/Datatable.vue';
  import NavBar from './components/header/NavBar.vue';

  export default {
    components: {
        Loading,
        Datatable,
        NavBar
    }
  };


  document.addEventListener("DOMContentLoaded",()=>{
    console.log("loaded");

    setTimeout(()=>{
        document.getElementById("loading-area").style.display = "none";
        console.log("wait is done")
    },2000)

  })
  </script>
