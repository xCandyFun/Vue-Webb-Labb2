<script setup>
import {RouterLink, RouterView} from 'vue-router'
import GreetingTime from "@/components/GreetingTime.vue";


const emit = defineEmits(['theChangeFont'])

  function onChange(event){
  console.log(event.target.value)
  emit("theChangeFont", event.target.value)
    }

</script>

<template>
  <div>
  <GreetingTime />
  </div>
  <div id="ChangeStyle">
      <select @change="onChange" id="Dropdown">
        <option value="1">Time New Roman</option>
        <option value="2">Arial</option>
        <option value="3">Calibri</option>
        <option value="4">Comic Sans</option>
      </select>
  </div>
  <RouterView/>
</template>

<style scoped>
select#Dropdown{
  background: #f9e2ca;;
}
div {
  text-align: center;
  padding-top: 10px;
}

div#ChangeStyle{
  padding-right: 20px;
}

select{
  float: right;
  color: #7A5D3E;
}
</style>