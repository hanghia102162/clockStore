<template>
  <header class="sticky top-0 z-50 bg-gray-900 text-white">
    <div
      class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-10 py-4 flex justify-between items-center"
    >
      <h1 class="tracking-[4px] font-semibold text-sm sm:text-base">
        Nghia Atelier
      </h1>

      <nav class="hidden md:flex gap-8 text-sm">
        <a
          @click="handelHome"
          class="relative after:content-[''] after:absolute after:left-0 after:bottom-0 after:h-[2px] after:w-0 after:bg-yellow-400 hover:after:w-full after:transition-all after:duration-500 cursor-pointer hover:text-yellow-500 hover:scale-110 hover:translate-y-[-5px] duration-500 transition-all"
          >TRANG CHỦ</a
        >
        <a
          @click="handleCollections"
          class="relative after:content-[''] after:absolute after:left-0 after:bottom-0 after:h-[2px] after:w-0 after:bg-yellow-400 hover:after:w-full after:transition-all after:duration-500 cursor-pointer hover:text-yellow-500 hover:scale-110 hover:translate-y-[-5px] duration-500 transition-all"
          >SẢN PHẨM</a
        >
        <a
          @click="handelWorkmanship"
          class="relative after:content-[''] after:absolute after:left-0 after:bottom-0 after:h-[2px] after:w-0 after:bg-yellow-400 hover:after:w-full after:transition-all after:duration-500 cursor-pointer hover:text-yellow-500 hover:scale-110 hover:translate-y-[-5px] duration-500 transition-all"
          >TAY NGHỀ</a
        >

        <!-- <a class="hover:text-yellow-500">KHO LƯU TRỮ</a> -->
      </nav>

      <div class="md:flex hidden gap-4 text-sm">
        <button @click="handelCart">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="size-6 cursor-pointer hover:text-yellow-600 hover:scale-110 hover:translate-y-[-5px] duration-500 transition-all"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 0 0-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 0 0-16.536-1.84M7.5 14.25 5.106 5.272M6 20.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Zm12.75 0a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Z"
            />
          </svg>
        </button>
        <button @click="handleAccount">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="size-6 cursor-pointer hover:text-yellow-600 hover:scale-110 hover:translate-y-[-5px] duration-500 transition-all"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15.75 6a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0ZM4.501 20.118a7.5 7.5 0 0 1 14.998 0A17.933 17.933 0 0 1 12 21.75c-2.676 0-5.216-.584-7.499-1.632Z"
            />
          </svg>
        </button>
      </div>

      <div class="relative md:hidden">
        <!-- ICON -->
        <button class="text-xl" @click="toggleMenu">☰</button>

        <!-- MENU (HIỆN NGAY DƯỚI ICON) -->
        <div
          v-if="isOpen"
          class="absolute right-0 cursor-pointer mt-2 w-48 bg-white shadow-lg rounded-lg p-3 flex flex-col gap-2 text-sm z-50 text-black"
        >
          <a @click="handelHome" class="cursor-pointer hover:text-yellow-600"
            >TRANG CHỦ</a
          >
          <a
            @click="handleCollections"
            class="cursor-pointer hover:text-yellow-600"
            >SẢN PHẨM</a
          >
          <a
            @click="handelWorkmanship"
            class="cursor-pointer hover:text-yellow-600"
            >TAY NGHỀ</a
          >
          <hr />
          <a @click="handelCart" class="cursor-pointer hover:text-yellow-600"
            >Cart</a
          >
          <a @click="handleAccount" class="cursor-pointer hover:text-yellow-600"
            >Account</a
          >
        </div>
      </div>
    </div>
  </header>
</template>
<script setup>
import { ref } from "vue";
const emit = defineEmits([
  "accountClick",
  "clickCollections",
  "clickHome",
  "clickWorkmanship",
  "clickCart",
]);

const handleAccount = () => {
  emit("accountClick");
};
const handleCollections = () => {
  emit("clickCollections");
};
const handelHome = () => {
  emit("clickHome");
};
const handelWorkmanship = () => {
  emit("clickWorkmanship");
};
const handelCart = () => {
  emit("clickCart");
};

const isOpen = ref(false);
const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};
</script>
