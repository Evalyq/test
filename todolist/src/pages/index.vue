<template>
    <div class="container">
        <abc @myfu="myfu"></abc>
        <myComponent :show.sync='valueChild' style="padding: 30px 20px 30px 5px;border:1px solid #ddd;margin-bottom: 10px;"></myComponent>
        <button @click="changeValue">toggle</button>
    </div>
</template>
<script>
    import abc from '../components/a.vue'
import myComponent from '../components/b.vue'
export default {
    data(){
        return{
            valueChild:true,
        }
    },
    components:{
        abc
    },
    methods:{
        myfu (message) {
            console.log(message)
        },
        changeValue(){
            this.valueChild = !this.valueChild
        }
    }
}
</script>
