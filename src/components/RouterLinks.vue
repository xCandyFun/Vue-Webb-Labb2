<script setup>
import {RouterLink, RouterView} from 'vue-router'
import GreetingTime from "@/components/GreetingTime.vue";


const emit = defineEmits(['theChangeFont'])

  function onChange(event){
  console.log(event.target.value)
  emit("theChangeFont", event.target.value)
  //if value === 1 then
    }

</script>

<template>
  <div>
  <GreetingTime />
  </div>
  <div>
    <nav>
<!--      <button id="HomeButton" >-->
<!--        <RouterLink to="/" class="LinkStyle">Home</RouterLink>-->
<!--      </button>-->
<!--      <button id="SettingsButton">-->
<!--        <RouterLink to="/settings" class="LinkStyle">Settings</RouterLink>-->
<!--      </button>-->
    </nav>

    <select @change="onChange">
      <option value="1">Time New Roman</option>
      <option value="2">Arial</option>
      <option value="3">Calibri</option>
      <option value="4">Comic Sans</option>
    </select>
  </div>
  <RouterView/>
</template>

<style scoped>
div {
  text-align: center;
  padding-top: 10px;
}

button#HomeButton{
  margin-right: 10px;
}
.LinkStyle{
  text-decoration: none;
}
select{
  float: right;

}
</style>