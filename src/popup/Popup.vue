<script setup>
import { useImage } from '@vueuse/core'
const avatarUrl = 'https://s1.ax1x.com/2023/01/23/pSYuIYD.png'
const { isLoading } = useImage({ src: avatarUrl })

const to_left = () => {
  document.getElementsByClassName('img')[0].classList.remove('toright')
}
const to_right = () => {
  document.getElementsByClassName('img')[0].classList.add('toright')
}
</script>

<template>
  <main class="w-[384px] h-[256px] text-center text-light-700 bg-[#138385] font-sans">
    <div class="h-100% w-100% flex flex-row justify-between p-5 items-center">
      <span v-if="isLoading" class="animate-pulse bg-[#0A4445] w-35 h-35 text-center font-black leading-34">Loading</span>
      <img v-else :src="avatarUrl" class="w-35 h-35 img duration-700">
      <div />
    </div>
    <footer class="bg-[#138385] ">
      <button class="i-carbon-caret-left hover:bg-[#1DCED1] bg-light-50" @click="to_left" />
      <button class="i-carbon-caret-right hover:bg-[#1DCED1] bg-light-50" @click="to_right" />
    </footer>
  </main>
</template>

<style>
.toright{
  @apply translate-x-142% transition
}
</style>
