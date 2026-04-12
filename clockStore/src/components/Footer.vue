<template>
  <footer class="bg-gray-900 text-gray-400 py-16 text-center">
    <h3 class="text-white font-bold mb-6">Nghia Atelier</h3>

    <div class="flex justify-center gap-8 text-sm mb-6">
      <a v-for="link in footer" :key="link">{{ link }}</a>
    </div>

    <p class="text-xs opacity-60">© 2024 Maison Nghia Atelier</p>
  </footer>
</template>
<script setup>
const footer = [
  "Chính sách bảo mật",
  "Điều khoản sử dụng",
  "Chính sách vận chuyển",
  "Liên hệ",
];
</script>
