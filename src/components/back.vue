<template>
  <div class="hello">
    <h1>tp-js-sdk-demo v2</h1>

    <div>
      
      <h3>1.11 tp.fullScreen</h3>
      <div class="demo-content">
        <button @click="fullScreen(1)">全屏 1</button>
        <button @click="fullScreen(0)">取消全屏 0</button>
   
      </div>
    </div>

    <div>
      <h3>1.10 tp.back</h3>
      <div class="demo-content">
        <button @click="back">Back 返回</button>
      </div>
    </div>
     
  </div>
</template>

<script>
import tp from 'tp-js-sdk';
import $ from 'jquery';

export default {
  name: 'Back',
  created() {
    window.tp = tp;
    console.log(tp);
  },
  methods: {
    fullScreen(num) {
        tp.fullScreen({fullScreen: +num});
    },
    back() {
        tp.back();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
button {
  padding: 4px 10px;
  -webkit-appearance: none;
  border: 1px solid #ddd;
  border-radius: 2px;
  background: #fff;
  line-height: 1.5;
}
div, p {
  word-break: break-all;
}

.item {
    border-bottom: 1px solid #f1f1f1;
    padding: 20px 10px;
}
</style>
