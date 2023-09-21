<script setup>
import {ref} from "vue";

 // namn: tomat, hur många 2st, pris
const Food = ref([]);
const inputFood = ref('')
const inputAmount = ref('')
const inputPrice = ref('')

function toAddFood(){
  const newShoppingItem = {
    name:inputFood.value,
    amount:inputAmount.value,
    price:inputPrice.value
  }
  Food.value.push(newShoppingItem);
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
        <h1>{{food.name}}</h1>
        <p>Amount: {{food.amount}}</p>
        <p>Price: {{food.price}}</p>
        <button @click="filterArray(food)">Remove</button>
      </li>
      <li id="input">
        <input type="text" v-model="inputFood" placeholder="Sak" required/>
        <input type="text" v-model="inputAmount" placeholder="Hur många?" required/>
        <input type="text" v-model="inputPrice" placeholder="Pris" required/>
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