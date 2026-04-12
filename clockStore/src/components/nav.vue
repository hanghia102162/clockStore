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

      <div class="flex gap-4 text-sm">
        <button @click="handelCart">Cart</button>
        <button @click="handleAccount">Account</button>
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
</script>
