<template>
    <div class="component5">
        <div class="title">Component5</div>
        <div>
            <span class="text-bold">text：</span>
            {{text}}
        </div>
        <button @click="addGrandParentCount">
            add count of Component3.vue
        </button>
    </div>
</template>

<script>
export default {
    name: "Component5",
    inject:['text','component3'],
    methods:{
        addGrandParentCount(){
            this.component3.addCount();
        }
    }
}
</script>

<style scoped>
.component5{
    width: 100%;
    padding: 20px;
    background-color: dodgerblue;
    margin-top: 20px;
}
</style>