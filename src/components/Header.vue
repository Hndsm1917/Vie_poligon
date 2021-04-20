
<template>
  <header>
    <div class="header__space"></div>
    <div class="header__main">
      <div class="container">
            <div class="logo">

            </div>
            <nav>

            </nav>
            <div class="search">
              
            </div>
        </div>
    </div>
    
  </header>
</template>

<script>

import { defineProps, reactive } from 'vue'

export default{
  data() {
    return{
      
    }
  },

}


</script>

<style scoped>
  header{

    width: 100%;
    height: auto;
    position: fixed;
    top: 0px;
    left: 0px;
  }
  .header__space{
    height: 80px;
    background-image: url(../assets/121.jpg) ;
    background-size: cover;
  }
  .header__main{
    background: #42b983;
    height: 40px;
  }
</style>