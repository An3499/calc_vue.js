<template>
<Output :value='localValue'/>
<div class='button__container'>
    <Button
    v-for='btn in buttons'
    :key="btn" 
    :text="btn"
    @btnClick="onBtnClick" />
</div>
</template>

<script>
import {defineComponent} from 'vue';
import Button from './components/Button.vue';
import Output from './components/Output.vue';

export default defineComponent({
    name: 'App',
    components: {
        Button,
        Output
    },
    data() {
        return {
            buttons: [
                '1', '2', '3', '4', '5', '6', '7', '8', '9', '0', '+', '-', '/', '*', '%', '=','C','<'
            ],
            localValue: ''
        }
    },
    methods: {
        onBtnClick(text) {
          if(text == '='){
            this.$data.localValue=eval(this.$data.localValue)
          } else if(text =='C'){
            this.$data.localValue=''
          } else if(text =='&lt;'){
            this.$data.localValue=this.$data.localValue.slice(0,-1);
          } else{
            this.$data.localValue+=text;
          }
          
        }
    }
})
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background-color: yellow;
}

.button__container {
    display: flex;
    flex-wrap: wrap;
    width: 250px;
    align-items: center;
    justify-content: center;
}
</style>
