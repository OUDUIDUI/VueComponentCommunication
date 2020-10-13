<template>
    <div class="component3">
        <div class="title">Component3</div>
        <div>
            <span class="text-bold">count：</span>
            {{count}}
        </div>
        <button @click="addChildrenCount">
            add count of Component4.vue
        </button>
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: "Component3",
    provide(){
        return{
            text:this.text,
        }
    },
    data() {
        return {
            text: 'Text From Component3.vue',
            count: 0
        }
    },
    mounted() {
        this.$on("changeCount",count => this.count = count);
        console.log(this.$children[0]);
    },
    methods:{
        addChildrenCount(){
            this.$children[0].$emit('addCount');
        }
    }
}
</script>

<style scoped>
.component3{
    width: 100%;
    padding: 20px;
    background-color: aquamarine;
}
</style>