<template>
    <div class="component5">
        <div class="title">Component5</div>
        <div>
            <span class="text-bold">text：</span>
            {{text}}
        </div>
    </div>
</template>

<script>
export default {
    name: "Component5",
    inject:['text'],
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