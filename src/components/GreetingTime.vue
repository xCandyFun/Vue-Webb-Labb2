<script setup>
const date = new Date();
const time = date.getHours();

</script>

<template>
  <div>
    <h1 v-if="time<10"><span>Good morning</span></h1>
    <h1 v-else-if="time<12"><span>Good day</span></h1>
    <h1 v-else-if="time<18"><span>Good afternoon</span></h1>
    <h1 v-else><span>Good evening</span></h1>
  </div>
</template>


<style scoped>
div {
  text-align: center;
}

span {
  border-style: solid;
  border-color: black;
  background: #f9e2ca;
  padding: 5px 20px;

}
</style>