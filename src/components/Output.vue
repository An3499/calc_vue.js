<template>
    <input class='output' v-model='value'/>
</template>

<script>
import {defineComponent} from 'vue';

export default defineComponent({
    props: {
        value:String
    }
})
</script>

<style>
.output {
    width: 230px;
    height: 5vh;
    margin-bottom: 3px;
    font-size: 30px;
}

</style>