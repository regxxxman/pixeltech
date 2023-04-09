<template>
  <div class="">
    <div class="container mx-auto pl-5 border rounded">
      <nav
        class="h-20 dark:text-white flex justify-between [&>*]:my-auto last:pr-5"
      >
        <NuxtLink class="text-3xl font-black">
          <span
            class="animate-text bg-gradient-to-r from-pink-500 via-red-500 to-yellow-500 bg-clip-text text-transparent"
            >Pixel</span
          >Tech
        </NuxtLink>
        <ul class="dark:text-gray-300 font-light flex [&>*]:pl-3">
          <li>Главная</li>
          <li>О нас</li>
          <li>Начать играть</li>
          <li>Форум</li>
        </ul>
        <div class="flex gap-x-4">
          <button class="btn">Войти</button>
          <button class="btn">Регистрация</button>
        </div>
      </nav>
    </div>
  </div>
</template>
