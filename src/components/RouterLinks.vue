<script setup>
import {RouterLink, RouterView} from 'vue-router'
import GreetingTime from "@/components/GreetingTime.vue";
</script>

<template>
  <div>
  <GreetingTime />
  </div>
  <div>
    <nav>
      <button id="HomeButton" >
        <RouterLink to="/" class="LinkStyle">Home</RouterLink>
      </button>
      <button id="SettingsButton">
        <RouterLink to="/settings" class="LinkStyle">Settings</RouterLink>
      </button>
    </nav>
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
</style>