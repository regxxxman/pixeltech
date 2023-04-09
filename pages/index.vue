<template>
  <div class="container mx-auto px-4 pt-40 pb-20 text-white">
    <div class="flex">
      <div class="flex flex-col basis-1/2 gap-y-8">
        <h1 class="text-5xl font-extrabold dark:text-white h-36">
          <span id="animation-text">
            <!-- {{ text[0] }} -->
          </span>
          <!-- Откройте для себя инновации в
          <span
            class="animate-text bg-gradient-to-r from-teal-500 via-purple-500 to-orange-500 bg-clip-text text-transparent"
            >Minecraft</span
          >
          вместе с нами! -->
          <span id="cursor"> _</span>
        </h1>
        <p class="text-xl font-light leading-loose text-gray-200">
          На нашем сервере нового поколения вы найдете все, что ищете -
          комфортную атмосферу, захватывающий геймплей, ответственную модерацию
          и отличную игровую экономику.
        </p>

        <div class="btn-group [&>*]:h-20 w-1/2">
          <button class="btn btn-block">Войти</button>
          <button class="btn btn-block">Регистрация</button>
        </div>
      </div>
      <div class="text-white">2</div>
    </div>
  </div>
</template>

<script setup>
import gsap from 'gsap'
import TextPlugin from 'gsap/TextPlugin'
import SplitText from 'gsap-trial/SplitText'

if (process.client) {
  gsap.registerPlugin(SplitText)
}
const text = [
  'Откройте для себя инновации в Minecraft вместе с нами!',
  'Для тех, кто готов идти в ногу с новыми технологиями.',
  'Развивайтесь и создавайте новое в Minecraft.',
]
const colortext = [6, 3, 1]

onMounted(() => {
  gsap.registerPlugin(TextPlugin)

  let tlMaster = gsap.timeline({ repeat: -1 })

  text.forEach((text) => {
    let tlText = gsap.timeline({
      repeat: 1,
      yoyo: true,
      repeatDelay: 5,
    })
    tlText.to('#animation-text', {
      duration: 1,
      text: text,
    })
    tlMaster.add(tlText)
  })
  gsap.to('#cursor', {
    opacity: 0,
    repeat: -1,
    yoyo: true,
    duration: 0.5,
    ease: 'power2.inOut',
  })
})
</script>
