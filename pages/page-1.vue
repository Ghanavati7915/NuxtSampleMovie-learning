<script setup lang="ts">
let age = ref(0);
const name = ref('');
const user = reactive({
  name : '',
  family : '',
  age : 0,
  father : ''
});
const seed = (_name : string, _age : number) => {
  user.name = _name;
  user.age = _age;
  name.value = _name
  age.value = _age
}
setTimeout(()=>{
  seed('Ali' , 30)
},2000)
</script>

<template>
  <div>
    <h1> Page 1 [ index ] </h1>

    Age :
    <input type="text" v-model="user.age">

    Name :
    <input type="text" v-model="user.name">

    <p class="myParaph"> [ 1 ] Hello mr.{{user.name}} - Age : {{user.age}}</p>
    <p class="myParaph"> [ 2 ] Hello mr.{{name}} - Age : {{age}}</p>

    <h2 @click="age++"> Plus </h2>
    <h2 @click="age--"> Mines </h2>
    <h2 @click="seed('Reza',27)"> Seed </h2>
  </div>
</template>

<style scoped>
.myParaph{
  color:red;
  font-size: larger;
}
</style>