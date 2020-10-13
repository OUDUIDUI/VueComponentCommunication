<template>
    <div class="component1">
        <div class="title">Component1</div>
        <div>
            <span class="text-bold">text：</span>
            {{text}}
        </div>
        <div>
            <span class="text-bold">count：</span>
            {{count}}
        </div>
        <button @click="addParentCount">
            add count of App.vue
        </button>
    </div>
</template>

<script>
export default {
    name: "Component1",
    props:{
        text:{
            type:String
        }
    },
    data(){
        return{
            text1: 'Text From Component1.vue',
            count: 0
        }
    },
    mounted(){
        this.$EventBus.$on('changeCount',(count)=> this.count = count);
    },
    methods:{
        addCount(){
            this.count++;
        },
        addParentCount(){
            this.$emit('addCount')
        }
    }
}
</script>

<style scoped>
.component1{
    width: 100%;
    padding: 20px;
    background-color:  aqua;
}
</style>
