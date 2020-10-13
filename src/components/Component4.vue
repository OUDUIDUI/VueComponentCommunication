<template>
    <div class="component4">
        <div class="title">Component4</div>
        <div>
            <span class="text-bold">text：</span>
            {{text}}
        </div>
        <div>
            <span class="text-bold">text：</span>
            {{text2}}
        </div>
        <div>
            <span class="text-bold">count：</span>
            {{count}}
        </div>
        <div>
            <input type="number" placeholder="Number..." v-model="value">
        </div>
        <button @click="changeParentCount">
            change count of Component3.vue
        </button>
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: "Component4",
    inject:['text'],
    data() {
        return {
            text1: 'Text From Component4.vue',
            text2:'',
            count: 0,
            value:''
        }
    },
    mounted() {
        this.$on('addCount',() => this.count++);
        this.text2 = this.$parent.text1;
    },
    methods:{
        changeParentCount(){
            this.$parent.$emit('changeCount',this.value)
        },
    }
}
</script>

<style scoped>
.component4{
    width: 100%;
    padding: 20px;
    background-color: bisque;
    margin-top: 20px;
}
</style>