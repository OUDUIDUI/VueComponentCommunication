<template>
  <div id="app">
      <div class="app">
          <div class="title">App.vue</div>
          <div>
              <span class="text-bold">text：</span>
              {{text2}}
          </div>
          <div>
              <span class="text-bold">count：</span>
              {{count}}
          </div>
          <button @click="ChildrenCount">
              add count of Component1.vue
          </button>
      </div>
      <component1 :text="text1" @addCount="addCount" ref="component1" />
      <component2 />
      <component3>
          <component4>
              <component5></component5>
          </component4>
      </component3>
      <component6 />
  </div>
</template>

<script>
import Component1 from "@/components/Component1";
import Component2 from "@/components/Component2";
import Component3 from "@/components/Component3";
import Component4 from "@/components/Component4";
import Component5 from "@/components/Component5";
import Component6 from "@/components/Component6";

export default {
    name: 'App',
    components: {
        Component1,
        Component2,
        Component3,
        Component4,
        Component5,
        Component6
    },
    data(){
        return{
            text1:"Text From App.vue",
            text2:'',
            count:0
        }
    },
    mounted() {
        this.text2 = this.$refs.component1.text1 || '';
    },
    methods:{
        addCount(){
            this.count++;
        },
        ChildrenCount(){
            this.$refs.component1.addCount();
        }
    }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}

.app{
    width: 100%;
    padding: 20px;
}

.title{
    line-height: 1.5;
    font-weight: bold;
    font-size: 20px;
}

.text-bold{
    font-weight: bold;
}

input{
    margin-top: 10px;
    padding: 5px 10px;
    height: 40px;
    border: 1px solid #999;
}

button{
    cursor: pointer;
    padding: 0 20px;
    color: #fff;
    background-color: #333;
    line-height: 40px;
    border: 1px solid #333;
    border-radius: 20px;
    margin-top: 10px;
}

button:focus,input:focus{
    outline: none;
}
</style>
