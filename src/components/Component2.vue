<template>
    <div class="component2">
        <div class="title">Component2</div>
        <div>
            <input type="number" placeholder="Number..." v-model="value">
        </div>
        <button @click="changeComponent1Count">
            change count of Component1
        </button>
    </div>
</template>

<script>
export default {
    name: "Component2",
    data() {
        return {
            value:''
        }
    },
    methods:{
        changeComponent1Count(){
            this.$EventBus.$emit("changeCount",this.value)
        }
    }
}
</script>

<style scoped>
.component2{
    width: 100%;
    padding: 20px;
    background-color: antiquewhite;
}
</style>