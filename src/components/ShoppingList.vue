<script setup>
import {ref} from "vue";

const Food = ref([]);

const inputFood = ref('')

function toAddFood(){
  Food.value.push(inputFood.value);
}

const filterArray = (food) =>{
  Food.value = Food.value.filter((removeFood) => removeFood !== food)
}
</script>

<template>
  <div>
    <h2>Shopping list</h2>
    <ol>
      <li v-for="food in Food" :key="food">
        {{food}}
        <button @click="filterArray(food)">Remove food</button>
      </li>
      <li id="input">
        <input type="text" v-model="inputFood"/>
      </li>
      <li id="input">
      </li>
      <li id="input">
        <button @click="toAddFood">Add new food</button>
      </li>
    </ol>
  </div>
</template>


<style scoped>
div{
  text-align: center;
}
h2{
  text-align: center;
}
li{
  list-style-position: inside;
}
li#input{
  list-style: none;
}
</style>