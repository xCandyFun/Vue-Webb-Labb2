<script setup>
import {ref} from "vue";

// namn: tomat, hur många 2st, pris
const Food = ref([]);
const inputFood = ref('')
const inputAmount = ref('')
const inputPrice = ref('')

function toAddFood() {
  const newShoppingItem = {
    name: inputFood.value,
    amount: inputAmount.value,
    price: inputPrice.value
  }
  Food.value.push(newShoppingItem);
}

const filterArray = (food) => {
  Food.value = Food.value.filter((removeFood) => removeFood !== food)
}
</script>

<template>
  <div>
    <h2><span>Shopping list</span></h2>
    <ol>
      <li v-for="food in Food" :key="food">
        <a id="NAP">Product: {{ food.name }}</a>
        <a id="NAP">Amount: {{ food.amount }}</a>
        <a id="NAP">Price: {{ food.price }}kr</a>
        <button class="button-3" @click="filterArray(food)" role="button">Remove</button>
        <p></p>
      </li>
      <li></li>
      <li>
        <a><input type="text" v-model="inputFood" placeholder="Product" required/></a>
        <a><input type="text" v-model="inputAmount" placeholder="Amount" required/></a>
        <a><input type="text" v-model="inputPrice" placeholder="Price" required/></a>
      </li>
      <li>
      </li>
      <li>
        <button class="button-21" @click="toAddFood" role="button">Add new food</button>
      </li>
    </ol>
  </div>
</template>


<style scoped>
div {
  text-align: center;
}

h2 {
  text-align: center;
}

span {
  background: #f9e2ca;
  border-style: solid;
  border-color: black;
  padding: 5px 20px;
}

ol{
  list-style: none;
}

a {
  padding-right: 5px;
}


.button-21 {
  align-items: center;
  appearance: none;
  background-color: #3EB2FD;
  background-image: linear-gradient(1deg, #4F58FD, #149BF3 99%);
  background-size: calc(100% + 20px) calc(100% + 20px);
  border-radius: 100px;
  border-width: 0;
  box-shadow: none;
  box-sizing: border-box;
  color: #FFFFFF;
  cursor: pointer;
  display: inline-flex;
  font-family: CircularStd, sans-serif;
  font-size: 1rem;
  height: auto;
  justify-content: center;
  line-height: 1.5;
  padding: 6px 20px;
  position: relative;
  text-align: center;
  text-decoration: none;
  transition: background-color .2s, background-position .2s;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: top;
  white-space: nowrap;
}

.button-21:active,
.button-21:focus {
  outline: none;
}

.button-21:hover {
  background-position: -20px -20px;
}

.button-21:focus:not(:active) {
  box-shadow: rgba(40, 170, 255, 0.25) 0 0 0 .125em;
}

.button-3 {
  appearance: none;
  background-color: #2ea44f;
  border: 1px solid rgba(27, 31, 35, .15);
  border-radius: 6px;
  box-shadow: rgba(27, 31, 35, .1) 0 1px 0;
  box-sizing: border-box;
  color: #fff;
  cursor: pointer;
  display: inline-block;
  font-family: -apple-system, system-ui, "Segoe UI", Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
  font-size: 14px;
  font-weight: 600;
  line-height: 20px;
  padding: 6px 16px;
  position: relative;
  text-align: center;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: middle;
  white-space: nowrap;
}

.button-3:focus:not(:focus-visible):not(.focus-visible) {
  box-shadow: none;
  outline: none;
}

.button-3:hover {
  background-color: #2c974b;
}

.button-3:focus {
  box-shadow: rgba(46, 164, 79, .4) 0 0 0 3px;
  outline: none;
}

.button-3:disabled {
  background-color: #94d3a2;
  border-color: rgba(27, 31, 35, .1);
  color: rgba(255, 255, 255, .8);
  cursor: default;
}

.button-3:active {
  background-color: #298e46;
  box-shadow: rgba(20, 70, 32, .2) 0 1px 0 inset;
}

a#NAP {
  border-style: solid;
  border-color: #ffb857;
  background: #f9e2ca;
  padding: 5px 20px;
  color: #7A5D3E;
}

input {
  appearance: none;
  border: none;
  outline: none;
  border-bottom: .2em solid #ffb857;
  background: #f9e2ca;
  border-radius: .2em .2em 0 0;
  padding: .4em;
}
</style>