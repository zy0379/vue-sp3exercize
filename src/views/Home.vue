<template xmlns:margin-bottom="http://www.w3.org/1999/xhtml"
          xmlns:v-on="http://www.w3.org/1999/xhtml">
<div>
  <div style="background-color: darkgray; margin: 0 auto; text-align: center;font-size: 18px; font-weight: 700;">
    喵的，学习使我快乐！！！
  </div>
  <div>
    {{ cc }}
  </div>
  <div>
    {{ bb }}
  </div>
  <div>
    {{ aa }}
  </div>
  <div>
    {{ data.a }}
    {{ data.b }}
    {{ data.c }}
    {{ data.d }}
  </div>
  <div>
    <input v-model="data.a" style="width: 1000px;">
  </div>
  <div style="margin-bottom: 20px" >
    <span style="color: red" v-if="data.name === '佩奇'">小猪佩奇</span>
    <span style="color: blue" v-if="data.name === '乔治'">小猪乔治</span>
  </div>
  <div style="display: flex; margin-bottom:20px">
    <div @click="show(item)" style="width:300px;height:300px;text-align: center;line-height: 300px;font-size: 30px;margin-right: 10px;background-color: green" v-for="item in data.arr">{{item}}</div>
    <div>
      <select>
        <option v-for="item in data.fruit">{{item}}</option>
      </select>
    </div>
  </div>
  <div style="margin-bottom: 20px">
    <button @click="click">点击加功德</button>
  </div>
  <div>
    <div :style="data.box"></div>
    <div>
      <img :src="data.img" alt="">
    </div>
  </div>
</div>
</template>

<script setup>
import {reactive, ref} from 'vue';
const aa = ref("啊，可爱的沙雕哦,你可以在这里修改以上昵称")
const bb = ref("以上昵称")
const cc = ref("你个沙雕")

const data = reactive({
  a:123,
  b:"门前大桥下",
  c:"123456",
  d:false,
  arr:[4,5,6],
  fruit:["苹果","香蕉","橘子"],
  name:'乔治',
  box:{
    display: 'flex',
    width: '100px',
    height: '100px',
    backgroundColor: 'yellow'
  },
  img:'https://ts1.tc.mm.bing.net/th/id/OIP-C.XS6EtBzAmWWa31cfFvcx6QHaHa?w=195&h=211&c=8&rs=1&qlt=90&o=6&dpr=1.5&pid=3.1&rm=2'
})
const click =()=>{
  alert("功德加一");
}

const show = (value) =>{
  alert(value);
}
</script>