<template>
    <section>
        <div class="container">
            <div class="main__heading">
                <h1>All news</h1>
                <span>Opens {{ openRate }}</span>
                <br>
                <span>Readings {{ readings }}</span>
            </div>
            <div class="homeCard__grid">
                <HomeCard 
                    v-for="item in news"
                    v-bind:key="item.title"
                    v-bind:text='item.text'
                    v-bind:title="item.title"
                    v-bind:is-open="item.isOpen"
                    v-on:open-smth="openNews"
                    v-on:read-smth="readNews"
                />
            </div>


        </div>
    </section>
    

</template>

<script>
import { watch } from 'vue';
import HomeCard from './Home_card.vue'

export default{
    data() {
        return {
            openRate: 0,
            readings: 0,
            news: [
                {
                    title: 'news1',
                    text: 'Один из самых важных блоков в курсе, где вы узнаете все о компонентах. В блоке мы напишем 2 разных приложения и создадим более 5 различных UI компонентов как в реальной разработке. Блок расскажет про абсолютно все составляющие, которые есть в компонентах: взаимодействие, slots, асинхронные и динамические компоненты и тонна примеров.',
                    isOpen: false
                },
                {
                    title: 'news2',
                    text: 'Одним из наиболее важных обновлений в Vue 3 является появление альтернативного синтаксиса Composition API. В этом блоке вы узнаете все, чтобы полностью пользоваться данными синтаксисом на практических примерах. Помимо этого вы узнаете как работать',
                    isOpen: false
                },
                {
                    title: 'news3',
                    text: 'Один блоке вы узнаете абсолютно все про Vuex. Вы узнаете как работать с данными, какие есть лучшие практики по их программированию и структуриро',
                    isOpen: false
                },
            ],
        }
    },
    methods: {
        openNews(){
            this.openRate++
        },
        readNews(){
            this.readings++
        }
    },
    components: {
        HomeCard
    }
}

</script>

<style lang="scss">
    $vue-color: #42b983;
    $vue-light: #d6ffec;
    .activ{
        color: seagreen;
    }
    .block{
        display: flex;
        flex-direction: column;
        background: white;
        border-radius: 15px;
        height: auto;
        margin-bottom: 20px;
        width: 100%;
        padding: 0.75em 2em;
        height: fit-content;
    }
    .more{
        width: auto;
        height: 40px;
        border: 1px solid $vue-color;
        border-radius: 15px;
        padding: 0.75em 2em;
        width: fit-content;
        margin: 20px 0px 0px;
        background: white;
        transition: 0.2s;
        color: $vue-color;
        &:hover{
            background: $vue-color;
            color: $vue-light;
        }
    }
    .homeCard__grid{
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 40px 80px;
    }
    h1{
        font-size: 30px;
        margin-bottom: 30px;
    }
</style>
