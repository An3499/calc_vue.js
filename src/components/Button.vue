<template>
    <div
     class='button'
     @click='onDivClick'>
     {{this.text}}
    </div>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
    props:{
        text: String
    },

    methods:{
        onDivClick(){
            this.$emit('btnClick',this.$el.innerHTML)
        }
    }
})
</script>

<style>
.button{
    width: 50px;
    height: 50px;
    background-color: aqua;
    margin-right: 0.5vw;
    margin-left: 0.5vw;
    margin-bottom: 1vw;
    font-size: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.button:active{
    opacity: 0.7;
    color: tomato;
}
</style>