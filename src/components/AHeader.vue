<template>
  <header class="flex gap-5 p-2 shadow-lg h-16 items-center">
    <div
        class="cursor-pointer"
        @click="$emit('toggle-drawer')"
    >
      Menu
    </div>

    <div class="flex flex-grow justify-center">
      This laboratory work 2
    </div>

    <div
        class="cursor-pointer"
    >
      Profile
    </div>
  </header>
</template>