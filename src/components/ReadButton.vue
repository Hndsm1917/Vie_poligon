<template>
    <button @click="readArticle">
        Read article
    </button>
</template>

<script>
    export default {
        data(){
            return{
                isRead: false
            }
        },
        methods: {
            readArticle(){
                this.isRead = true
                if(this.isRead == true){
                    this.$emit('read-smth')
                }
            }
        },
        props: {
            color: {
                type: String,

            }
        },
    }
</script>

<style lang="scss" scoped>
    button{
        
    }
</style>