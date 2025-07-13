<script setup>
import Slide from './components/Slide.vue';
import soundFile from "./assets/audios/audio.mp3"
import { ref } from 'vue';

const hideDialog = ref(false)

function handleAgree() {
  const audio = new Audio(soundFile)
  audio.loop = true
  audio.play();
  hideDialog.value = true
}


</script>

<template>
  <div class="h-screen flex flex-col justify-center">
    <div v-if="!hideDialog" class="container">
      <div class="px-4 py-5 border border-gray-200 rounded-lg">
        <p>Hãy bỏ chút thời gian nghe lời tâm sự của mình nhé </p>
        <div class="flex justify-end mt-2">
          <button 
            @click="handleAgree"
            class="bg-green-500 text-white py-2 px-4 rounded-lg "
          >
            Bắt đầu
          </button>
        </div>
      </div>
    </div>
    <Slide v-else />
  </div>
</template>

<style scoped>
.dialog {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 1000;
}
</style>
