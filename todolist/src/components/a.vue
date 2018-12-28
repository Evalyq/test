<template>
    <div class="container">
        <input
            type="checkbox"
            v-bind:checked="checked"
            v-on:change="$emit('change', $event.target.checked)"
            >
            <div class="qui-list">

                <span class="list-tips">{{tipsText}}</span>

                <!-- <qui-btn v-on:btnClickEvent='btnClickEvent1' :msg=msg class='small'></qui-btn> -->

                <component :is='currentView' v-on:btnClickEvent='clickEvent' :msg=msg class="small" keep-alive></component>

            </div>
        <div @click="handleFun">{{message}}</div>
    </div>
</template>
<script>
export default {
    model: {
        prop: 'checked',
        event: 'change'
    },
    props: {
        checked: Booleanm
        msg:{

            default:'上传'

        },

        tipsText:{

            default: '默认的文案1'

        },

        currentView:{

            default: 'qui-btn'

        }
    },
    data(){
        return {
            message:'sdsfs'
        }
    },
    methods:{
        handleFun(){
            this.$emit("myfu",this,message)
        },
        clickEvent:function(){

				alert('...')

			}
    }
}
</script>
