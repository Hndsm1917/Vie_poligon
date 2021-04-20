<template>
    <div class="block"
         v-bind:key="item">
        <h2>{{ title }}</h2>
        <button class="more" @click="open">
            {{ isNewsOpen ? 'Close' : 'Open' }}
        </button>
        <p v-if="isNewsOpen">
            {{ text }}
            <read-button :color="colour">

            </read-button>
        </p>

    </div>
            
</template>
<script>
import ReadButton from "./ReadButton.vue"
export default {
    props: {
        title: {
            type: String,
            required: true,
        },
        text: {
            type: String,
            required: true,
        },
        isOpen: {
            type: Boolean,
            default: false,
            required: false,
            validator(value){
                return value === true || value === false
            }
        }
    },
    data(){
        return {
            isNewsOpen: this.isOpen,
            colour: '#bdf'
        }
    },
    methods: {
        open(){
            this.isNewsOpen = !this.isNewsOpen;
            if(this.isNewsOpen){
                this.$emit('open-smth')
            }
            
        },

    },
    components: {
        'read-button': ReadButton
    }
}
</script>
