<template>
    <div class="component8">
        <div class="title">Component8</div>
        <div>
            <span class="text-bold">text：</span>
            {{text2}}
        </div>
        <button @click="addGrandparentCount">
            add count of Component6.vue
        </button>
    </div>
</template>

<script>
export default {
    name: "Component8",
    props:{
        text2:{
            type:String
        },
    },
    methods:{
        addGrandparentCount(){
            this.$emit('addCount');
        }
    }
}
</script>

<style scoped>
.component8{
    width: 100%;
    padding: 20px;
    background-color: cadetblue;
    margin-top: 20px;
}
</style>