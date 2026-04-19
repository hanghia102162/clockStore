<template>
  <div class="bg-[#0b0f1a] min-h-screen">
    <!-- MAIN -->
    <div
      class="max-w-7xl mx-auto p-4 sm:p-6 grid grid-cols-1 lg:grid-cols-3 gap-6 lg:gap-10"
    >
      <!-- CART -->
      <div class="lg:col-span-2">
        <h2 class="text-2xl font-semibold mb-6 text-white">
          Giỏ Hàng - Horology Prestige
        </h2>

        <div
          v-for="(item, index) in cart"
          :key="index"
          class="flex gap-6 mb-10 border-b pb-6 text-white"
        >
          <img :src="item.image" class="w-40 h-40 object-cover" />

          <div class="flex-1">
            <h3 class="font-semibold">{{ item.name }}</h3>
            <p class="text-gray-500 text-sm">{{ item.desc }}</p>

            <div class="flex items-center mt-3 gap-2">
              <button class="border px-3" @click="decrease(index)">-</button>
              <span>{{ item.quantity }}</span>
              <button class="border px-3" @click="increase(index)">+</button>
            </div>
          </div>

          <div class="text-yellow-600 font-semibold">
            {{ formatPrice(item.price * item.quantity) }}
          </div>
        </div>

        <!-- RECOMMEND -->
        <h3 class="mt-12 mb-4 font-semibold text-white">Có thể bạn sẽ thích</h3>

        <div class="grid grid-cols-4 gap-4">
          <div v-for="(p, i) in products" :key="i" class="bg-white p-3">
            <img :src="p.image" class="w-full h-32 object-cover" />
            <p class="mt-2 text-sm">{{ p.name }}</p>
            <p class="text-yellow-600">{{ formatPrice(p.price) }}</p>
          </div>
        </div>
      </div>

      <!-- SUMMARY -->
      <div class="bg-white p-6 shadow">
        <h3 class="font-semibold mb-4">THÔNG TIN ĐƠN HÀNG</h3>

        <div class="flex justify-between mb-2">
          <span>Tạm tính</span>
          <span>{{ formatPrice(subtotal) }}</span>
        </div>

        <div class="flex justify-between mb-2">
          <span>Vận chuyển</span>
          <span>{{ formatPrice(shipping) }}</span>
        </div>

        <div class="flex justify-between font-bold text-lg mt-4">
          <span>Tổng cộng</span>
          <span>{{ formatPrice(total) }}</span>
        </div>

        <button class="w-full mt-6 bg-yellow-500 py-3 font-semibold">
          TIẾN HÀNH THANH TOÁN
        </button>

        <p class="text-gray-400 text-sm mt-4">Miễn phí đổi trả trong 30 ngày</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const cart = ref([
  {
    name: "Vanguard Chrono",
    desc: "REF. 4260 - HẾT HÀNG GIỚI HẠN",
    price: 245000000,
    quantity: 1,
    image: "/img/nam1.jpg",
  },
  {
    name: "Royal Heritage",
    desc: "REF. 7405 - THIẾT KẾ ĐẶC BIỆT",
    price: 189500000,
    quantity: 1,
    image: "/img/nam2.jpg",
  },
]);

const products = ref([
  {
    name: "Hộp Xoay Đồng Hồ",
    price: 12000000,
    image: "/img/nam1.jpg",
  },
  {
    name: "Dây Da Heritage",
    price: 4200000,
    image: "/img/nam2.jpg",
  },
  {
    name: "Eclipse Moonphase",
    price: 30000000,
    image: "/img/nam3.jpg",
  },
  {
    name: "Kính Lúp Horology Kit",
    price: 2800000,
    image: "/img/nam4.jpg",
  },
]);

// METHODS
const increase = (i) => cart.value[i].quantity++;
const decrease = (i) => {
  if (cart.value[i].quantity > 1) cart.value[i].quantity--;
};

// COMPUTED
const subtotal = computed(() =>
  cart.value.reduce((sum, item) => sum + item.price * item.quantity, 0),
);

const shipping = computed(() => subtotal.value * 0.1);

const total = computed(() => subtotal.value + shipping.value);

// FORMAT
const formatPrice = (price) => price.toLocaleString("vi-VN") + " đ";
</script>
