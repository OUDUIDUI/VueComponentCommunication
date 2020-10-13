<template>
    <div class="component6">
        <div class="title">Component6</div>
        <div>
            <span class="text-bold">count：</span>
            {{count}}
        </div>

        <component7 :text1="text" :text2="text" @addCount="addCount" />
    </div>
</template>

<script>
import Component7 from "@/components/Component7";

export default {
    name: "Component6",
    components:{
        Component7
    },
    data() {
        return {
            text: 'Text From Component6.vue',
            count: 0
        }
    },
    methods:{
        addCount(){
            this.count ++
        }
    }
}
</script>

<style scoped>
.component6{
    width: 100%;
    padding: 20px;
    background-color: aliceblue;
}
</style>