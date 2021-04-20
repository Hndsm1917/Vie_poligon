<template>
  <section>
    <div class="container">
        <h1>HomeWork1</h1>
        <div class="block_show" v-cloak>
          <h2>{{ currentStep.title }}</h2>
          <p>{{ currentStep.text }}</p>
        </div>
          <ul class="pagination">
            <li 
              v-for="(step, idx) in steps"
              v-bind:key="step.idx"
              :class="{
                curentPagination: idx === currentIndex,
                donePagination: idx < currentIndex
              }"
            >
             
             <span @click="setIndex(idx)">{{idx + 1}}</span>
            </li>
          </ul>
        
        <button 
          @click ="prevSlide"
          :class ="currentIndex == 0 ? 'deactivate' : ''"
          >Previous
        </button>

        <button @click="nextSlide" v-if="currentIndex !== steps.length-1">Next</button>
        <button @click="reset" v-else>Reset</button>

        
    </div>  
  </section>
  
</template>

<script>


export default{
  data(){
      return{
          currentIndex: 0,
          active: true,
          steps: [
              {title: 'Основы', text: 'В блоке вы познакомитесь со всеми основами Vue.js на практике. На протяжении блока мы напишем реактивное приложение, в процессе разработки которого разберем вся базу фреймворка.'},
              {title: 'Компоненты', text: 'Один из самых важных блоков в курсе, где вы узнаете все о компонентах. В блоке мы напишем 2 разных приложения и создадим более 5 различных UI компонентов как в реальной разработке. Блок расскажет про абсолютно все составляющие, которые есть в компонентах: взаимодействие, slots, асинхронные и динамические компоненты и тонна примеров.'},
              {title: 'Роутер', text: 'В данном блоке вы узнаете все о том, как работает мультиязычность во Vue. Мы создадим миниклон Gmail в данном блоке, где вы на практике увидите как работать с динамическим роутером.'},
              {title: 'Vuex', text: 'В блоке вы узнаете абсолютно все про Vuex. Вы узнаете как работать с данными, какие есть лучшие практики по их программированию и структурированию. Все на практике.'},
              {title: 'Composition', text: 'Одним из наиболее важных обновлений в Vue 3 является появление альтернативного синтаксиса Composition API. В этом блоке вы узнаете все, чтобы полностью пользоваться данными синтаксисом на практических примерах. Помимо этого вы узнаете как работать совместно с Vue Router и Vuex.'},
          ]
      }
  },
  methods: {
    prevSlide() {
      this.currentIndex--
    },
    nextSlide() {
      this.currentIndex++
      if(this.currentIndex === this.steps.length - 1){
        last_slide = true
      }
    },
    reset(){
      this.currentIndex = 0;
    },
    setIndex(idx){
      this.currentIndex = idx
    }
  },
  computed: {
    currentStep(){
      return this.steps[this.currentIndex]
    }
  }
}
</script>

<style lang="scss" scoped>
  section{
    color: #7FB785;
    background: #434e45;
    height: 100vh;
    padding: 80px 0px;
  }
  section h1{
    font-size: 28px;
    margin-bottom: 20px;
  }
  .block_show{
    display: flex;
    flex-direction: column;
  }
  .block{
    display: none;
  }
  .activeClass{
    display: flex;
  }
  .deactivate{
    pointer-events: none;
    display: none;
  }
  .pagination{
    display: flex;
    padding-top: 60px;
    padding-bottom: 20px;
  }
  .pagination li{
      display: flex;
      justify-content: center;
      align-items: center;
      width: 25px;
      height: 25px;
      border-radius: 15px;
      background: #2c3e50;
      margin-right: 10px;
    }
  
  .pagination .curentPagination{
    background: #7FB785;
    color: rgb(36, 101, 187);
  }
   .pagination .donePagination{
    background: #91aa93;
    color: rgb(36, 101, 187);
  }
</style>

