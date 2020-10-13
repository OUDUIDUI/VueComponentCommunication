<template>
    <div class="component3">
        <div class="title">Component3</div>
        <div>
            <span class="text-bold">text：</span>
            {{text2}}
        </div>
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
            text:this.text1,
            Component3:this
        }
    },
    data() {
        return {
            text1: 'Text From Component3.vue',
            text2:'',
            count: 0
        }
    },
    mounted() {
        this.$on("changeCount",value => this.count = value);
        this.text2 = this.$children[0].text1;
    },
    methods:{
        addChildrenCount(){
            this.$children[0].$emit('addCount');
        },
        addCount(){
            this.count++;
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