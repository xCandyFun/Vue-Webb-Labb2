<script setup>
import RouterLinks from "@/components/RouterLinks.vue";
import {ref} from "vue";



const chosenFont = ref("");
function ChangeFontFamily(font){
  console.log("test", font)
  chosenFont.value=font;


}
</script>

<template>
    <div :class="{TNR: chosenFont === '1', Ari: chosenFont === '2', Cal: chosenFont === '3', CS: chosenFont === '4'}">
      <RouterLinks @the-change-font="ChangeFontFamily"/>
    </div>
</template>
<style scoped>

</style>
