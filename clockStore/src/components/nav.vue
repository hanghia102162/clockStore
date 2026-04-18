<template>
  <header class="sticky top-0 z-50 bg-[#e6e6e6] text-black">
    <div
      class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-10 py-4 flex justify-between items-center"
    >
      <h1 class="tracking-[4px] font-semibold text-sm sm:text-base">
        Nghia Atelier
      </h1>

      <nav class="hidden md:flex gap-8 text-sm">
        <a @click="handelHome" class="hover:text-yellow-600 cursor-pointer"
          >TRANG CHỦ</a
        >
        <a
          @click="handleCollections"
          class="hover:text-yellow-600 cursor-pointer"
          >SẢN PHẨM</a
        >
        <a
          @click="handelWorkmanship"
          class="hover:text-yellow-600 cursor-pointer"
          >TAY NGHỀ</a
        >

        <!-- <a class="hover:text-yellow-600">KHO LƯU TRỮ</a> -->
      </nav>

      <div class="md:flex hidden gap-4 text-sm">
        <button @click="handelCart">Cart</button>
        <button @click="handleAccount">Account</button>
      </div>

      <div class="relative md:hidden">
        <!-- ICON -->
        <button class="text-xl" @click="toggleMenu">☰</button>

        <!-- MENU (HIỆN NGAY DƯỚI ICON) -->
        <div
          v-if="isOpen"
          class="absolute right-0 cursor-pointer mt-2 w-48 bg-white shadow-lg rounded-lg p-3 flex flex-col gap-2 text-sm z-50"
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
