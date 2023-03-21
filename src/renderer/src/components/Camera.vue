<template>
  <main class="w-screen h-screen">
    <video class="object-cover"></video>
  </main>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'

onMounted(() => {
  const video = document.querySelector('video')
  const constraints = {
    video: true,
    audio: false
  }
  navigator.mediaDevices.getUserMedia(constraints).then((stream) => (video.srcObject = stream))
  video?.play()
})
</script>

<style scoped lang="less"></style>
