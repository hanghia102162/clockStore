<template>
  <section
    class="max-w-[1400px] mx-auto px-4 sm:px-6 lg:px-10 pb-20 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8"
  >
    <!-- WATCH -->
    <div
      v-for="watch in watches"
      :key="watch.name"
      class="group hover:text-yellow-500"
    >
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

        <button class="text-yellow-400 text-xs sm:text-sm hover:underline">
          Liên hệ báo giá
        </button>
      </div>
    </div>

    <!-- PROMO CARD -->
    <div class="bg-[#3a3f40] p-6 sm:p-8 flex flex-col justify-between">
      <div>
        <p class="text-yellow-400 text-xs mb-3">MASTER COMPLICATION</p>

        <h2 class="text-xl sm:text-2xl lg:text-3xl font-serif mb-4">
          The Perpetual
          <br />
          Tourbillon No.1
        </h2>

        <p class="text-gray-400 text-xs sm:text-sm leading-relaxed">
          A singular achievement in horological engineering featuring a
          hand-finished platinum case.
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
</template>
<script setup>
const watches = [
  {
    name: "Vanguard Chrono",
    price: "52.400 USD",
    image: "/img/nu1.jpg",
  },

  {
    name: "Royal Heritage",
    price: "46.000 USD",
    image: "/img/nu2.jpg",
  },

  {
    name: "Abyssal Deep",
    price: "38.900 USD",
    image: "/img/nu3.jpg",
  },

  {
    name: "Lunar Phase",
    price: "53.900 USD",
    image: "/img/nu4.jpg",
  },
  {
    name: "Abyssal Deep",
    price: "38.900 USD",
    image: "/img/nu5.jpg",
  },

  {
    name: "Lunar Phase",
    price: "53.900 USD",
    image: "/img/nu6.jpg",
  },
  {
    name: "Abyssal Deep",
    price: "38.900 USD",
    image: "/img/nu7.jpg",
  },

  {
    name: "Lunar Phase",
    price: "53.900 USD",
    image: "/img/nu8.jpg",
  },
];
</script>
