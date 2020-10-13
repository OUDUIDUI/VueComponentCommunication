<template>
    <div class="component7">
        <div class="title">Component7</div>
        <div>
            <span class="text-bold">text：</span>
            {{text1}}
        </div>
        <component8 v-bind="$attrs" v-on="$listeners" />
    </div>
</template>

<script>
import Component8 from "@/components/Component8";

export default {
    name: "Component7",
    props:{
        text1:{
            type:String
        }
    },
    components:{
        Component8
    }
}
</script>

<style scoped>
.component7{
    width: 100%;
    padding: 20px;
    background-color: hotpink;
    margin-top: 20px;
}
</style>