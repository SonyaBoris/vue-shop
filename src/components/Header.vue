<template>
  <header class="flex justify-between border-b border-slate-300 p-8">
    <div class="flex items-center">
      <img src="/logo.png" alt="logo" class="w-10 mr-5" />
      <div>
        <h2 class="text-xl font-bold uppercase">Vue sneakers</h2>
        <p class="text-slate-400">Магазин лучших кросовок</p>
      </div>
    </div>
    <ul class="flex items-center gap-10 text-gray-500">
      <li class="flex items-center gap-3 hover:text-black cursor-pointer">
        <img src="/cart.svg" alt="" />
        <b>1205 p</b>
      </li>
      <li class="flex items-center gap-3 hover:text-black cursor-pointer">
        <img src="/heart.svg" alt="" />
        <span>Закладки</span>
      </li>
      <li class="flex items-center gap-3 hover:text-black cursor-pointer">
        <img src="/profile.svg" alt="" />
        <span>Профиль</span>
      </li>
    </ul>
  </header>
</template>
