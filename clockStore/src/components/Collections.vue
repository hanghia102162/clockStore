<template>
  <div class="bg-[#1f2223] min-h-screen text-gray-200">
    <!-- HERO -->
    <!-- <section
      class="relative h-[160px] sm:h-[220px] lg:h-[280px] overflow-hidden"
    >
      <img
        src="https://images.unsplash.com/photo-1522312346375-d1a52e2b99b3"
        class="absolute w-full h-full object-cover"
      />

      <div class="absolute inset-0 bg-black/60"></div>

      <div
        class="relative max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-10 h-full flex flex-col justify-center"
      >
        <h1 class="text-2xl sm:text-4xl lg:text-5xl font-serif">
          Bộ Sưu Tập Lưu Trữ
        </h1>

        <p class="text-yellow-400 text-xs sm:text-sm tracking-[3px] mt-2">
          Những Cỗ Máy Thời Gian Di Sản
        </p>
      </div>
    </section> -->

    <!-- FILTER -->
    <div
      class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-10 py-6 flex justify-between items-center text-xs sm:text-sm"
    >
      <div class="flex gap-6">
        <button
          @click="handelOpenAll"
          class="text-yellow-400 border-b border-yellow-400 pb-1"
        >
          Tất cả
        </button>

        <button @click="handelOpenNam" class="hover:text-yellow-400">
          Đồng hồ nam
        </button>

        <button @click="handelOpenNu" class="hover:text-yellow-400">
          Đồng hồ nữ
        </button>
        <select
          class="px-4 py-2 bg-[#1f2223] rounded-md focus:outline-none focus:ring-2 focus:ring-yellow-400"
        >
          <option>Quý tộc</option>
          <option>Lịch lãm</option>
          <option>Pháp</option>
          <option>Thụy Điển</option>
          <option>Hy Lạp</option>
          <option>Bình dân</option>
        </select>
      </div>

      <span class="text-gray-400"> Newest Releases </span>
    </div>

    <!-- PRODUCTS -->
    <section
      v-show="openall"
      class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-10 pb-20 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8"
    >
      <!-- WATCH -->
      <div v-for="watch in watches" :key="watch.name" class="group">
        <div
          class="bg-black h-[200px] sm:h-[220px] lg:h-[240px] flex items-center justify-center overflow-hidden"
        >
          <img
            :src="watch.image"
            class="h-[150px] sm:h-[170px] lg:h-[180px] object-contain transition duration-500 group-hover:scale-110"
          />
        </div>

        <div class="mt-4 space-y-1">
          <h3 class="text-sm sm:text-base font-medium">
            {{ watch.name }}
          </h3>

          <p class="text-gray-400 text-xs sm:text-sm">${{ watch.price }}</p>

          <div class="w-full flex justify-between">
            <button class="text-yellow-400 text-xs sm:text-sm hover:underline">
              Liên hệ
            </button>
            <button class="text-yellow-400 text-xs sm:text-sm hover:underline">
              Thêm vào giỏ hàng
            </button>
          </div>
        </div>
      </div>

      <!-- PROMO CARD -->
      <div class="bg-[#3a3f40] p-6 sm:p-8 flex flex-col justify-between">
        <div>
          <p class="text-yellow-400 text-xs mb-3">Tinh Hoa Cơ Chế Phức Tạp</p>

          <h2 class="text-xl sm:text-2xl lg:text-3xl font-serif mb-4">
            Tourbillon
            <br />
            Vĩnh Cửu Số 1
          </h2>

          <p class="text-gray-400 text-xs sm:text-sm leading-relaxed">
            Tuyệt tác độc nhất của nghệ thuật chế tác thời gian, nổi bật với bộ
            vỏ bạch kim hoàn thiện thủ công đến từng chi tiết
          </p>
        </div>

        <div class="mt-6">
          <p class="text-lg sm:text-xl mb-3">$865,000</p>

          <button
            class="bg-yellow-500 text-black px-4 sm:px-6 py-2 text-xs sm:text-sm font-semibold hover:bg-yellow-400 transition"
          >
            Đặt ngay
          </button>
        </div>
      </div>
    </section>
    <!-- sticknam -->
    <StickNam v-show="openNam" />
    <!-- sticknu -->
    <StickNu v-show="openNu" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import StickNam from "./stickNam.vue";
import StickNu from "./stickNu.vue";
const openall = ref(true);
const openNam = ref(false);
const openNu = ref(false);
const handelOpenAll = () => {
  openall.value = true;
  openNam.value = false;
  openNu.value = false;
};
const handelOpenNam = () => {
  openall.value = false;
  openNam.value = true;
  openNu.value = false;
};
const handelOpenNu = () => {
  openall.value = false;
  openNam.value = false;
  openNu.value = true;
};
const watches = [
  {
    name: "Vanguard Chrono",
    price: "52.400 USD",
    image: "/img/nam1.jpg",
  },

  {
    name: "Royal Heritage",
    price: "46.000 USD",
    image: "/img/nam2.jpg",
  },

  {
    name: "Abyssal Deep",
    price: "38.900 USD",
    image: "/img/nam3.jpg",
  },

  {
    name: "Lunar Phase",
    price: "53.900 USD",
    image: "/img/nu3.jpg",
  },
  {
    name: "Abyssal Deep",
    price: "38.900 USD",
    image: "/img/nu4.jpg",
  },

  {
    name: "Lunar Phase",
    price: "53.900 USD",
    image: "/img/nu5.jpg",
  },
  {
    name: "Abyssal Deep",
    price: "38.900 USD",
    image: "/img/nu1.jpg",
  },

  {
    name: "Lunar Phase",
    price: "53.900 USD",
    image: "/img/nu4.jpg",
  },
];
</script>
