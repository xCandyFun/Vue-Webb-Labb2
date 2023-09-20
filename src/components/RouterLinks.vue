<script setup>
import {RouterLink, RouterView} from 'vue-router'
</script>

<template>
  <div>

  </div>
  <div>
    <nav>
      <button id="HomeButton" >
        <RouterLink to="/">Home</RouterLink>
      </button>
      <button id="SettingsButton">
        <RouterLink to="/settings">Settings</RouterLink>
      </button>
    </nav>
  </div>
  <div>

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


</style>