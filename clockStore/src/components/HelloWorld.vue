<template>
  <div class="font-sans bg-[#111827] text-gray-800">
    <!-- HERO -->
    <section class="h-screen relative flex items-center">
      <img
        src="/img/nam8.jpg"
        class="absolute inset-0 w-full h-full object-cover object-left object-top scale-x-[-1]"
      />

      <div class="absolute inset-0 bg-black/50"></div>

      <div class="flex items-center min-h-screen">
        <div class="relative z-10 max-w-5xl mx-auto text-white px-6 md:ml-30">
          <h2 class="uppercase tracking-widest mb-4 text-sm">
            Thành lập năm 1894 — Genève
          </h2>

          <h1
            data-aos="fade-up"
            data-aos-duration="2000"
            class="text-6xl md:text-7xl font-bold leading-tight mb-6"
          >
            Nhịp đập của <br />
            <span class="text-yellow-400 text-3xl md:text-7xl italic"
              >Sự hoàn hảo</span
            >
          </h1>

          <p
            class="max-w-lg mb-8 text-gray-200"
            data-aos="fade-up"
            data-aos-duration="2000"
          >
            Xin giới thiệu Grand Complication No. 7. Một bản giao hưởng của 418
            chi tiết được hoàn thiện thủ công.
          </p>

          <button
            class="bg-yellow-400 text-black px-8 py-4 uppercase text-sm"
            data-aos="zoom-in"
            data-aos-duration="2000"
          >
            Vui lòng liên hệ riêng để hỏi thêm thông tin.
          </button>
        </div>
      </div>
    </section>

    <!-- COLLECTIONS -->
    <section class="py-24 max-w-7xl mx-auto px-6">
      <h2 class="text-4xl font-bold mb-16 text-white">Bộ sưu tập hiện tại</h2>

      <div class="grid md:grid-cols-3 gap-10">
        <div
          v-for="(item, index) in collections"
          :key="item.title"
          :class="['group relative', index === 0 ? 'md:col-span-2' : '']"
        >
          <div class="overflow-hidden">
            <img
              :src="item.image"
              class="w-full h-80 object-cover group-hover:scale-110 transition"
            />
          </div>

          <div
            class="absolute inset-0 flex flex-col justify-end p-6 bg-black/30"
          >
            <h3 class="text-xl font-semibold text-white">
              {{ item.title }}
            </h3>

            <p class="text-gray-200">
              {{ item.desc }}
            </p>
          </div>
        </div>
        <!-- <div class="md:col-span-2 group">
          <div class="overflow-hidden">
            <img
              src="/img/82d77da87b578e9eec561a69b45d3922.jpg"
              alt=""
              class="w-full h-80 object-cover group-hover:scale-110 transition"
            />
          </div>
          <h3 class="mt-4 text-xl font-semibold">idfsadd</h3>

          <p class="text-gray-500">asdasda</p>
        </div>
        <div
          v-for="item in collections"
          :key="item.title"
          class="'group', index === 0 ? 'md:col-span-2' : ''"
        >
          <div class="overflow-hidden">
            <img
              :src="item.image"
              class="w-full h-80 object-cover group-hover:scale-110 transition"
            />
          </div>

          <h3 class="mt-4 text-xl font-semibold">
            {{ item.title }}
          </h3>

          <p class="text-gray-500">
            {{ item.desc }}
          </p>
        </div> -->
        <!--  -->
      </div>
    </section>

    <!-- CRAFT SECTION -->
    <section class="bg-[#0b0f1a] text-white py-28">
      <div
        class="max-w-7xl mx-auto grid md:grid-cols-2 gap-16 px-6 items-center"
      >
        <img
          src="/img/56615e3f81e281f4285e08ea7b7182ed.jpg"
          class="grayscale"
        />

        <div>
          <h2 class="text-yellow-400 uppercase tracking-widest mb-4">
            NGHỆ THUẬT CHẾ TÁC THỤY SĨ
          </h2>

          <h3 class="text-5xl font-bold mb-6">
            Tinh Hoa Cơ Khí Ẩn Sau Thời Gian
          </h3>

          <p class="text-gray-400 mb-8">
            Ẩn sau mỗi mặt số là cả một vũ trụ cơ khí tinh vi. Những nghệ nhân
            chế tác của chúng tôi tạo nên từng cỗ máy thời gian với độ chính xác
            tuyệt đối.
          </p>

          <ul class="space-y-4">
            <li v-for="item in craft" :key="item">— {{ item }}</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- PRODUCTS -->
    <section class="py-24">
      <div class="max-w-7xl mx-auto px-6">
        <h2 class="text-4xl font-bold mb-12 text-white">Tuyển Chọn Mới Nhất</h2>

        <div class="grid md:grid-cols-4 gap-10 pb-10">
          <div
            v-for="product in products"
            :key="product.name"
            class="border p-6 hover:scaler-1.1 hover:translate-y-[-5px] duration-500 transition-all hover:text-yellow-500"
          >
            <img :src="product.image" class="w-full h-64 object-cover mb-6" />

            <h3 class="text-xl font-bold text-white">
              {{ product.name }}
            </h3>

            <p class="text-gray-500 mb-4">
              {{ product.detail }}
            </p>

            <p class="font-bold text-yellow-600">
              {{ product.price }}
            </p>

            <button class="mt-6 border px-6 py-3 w-full">Khám phá</button>
          </div>
        </div>
      </div>
    </section>

    <!-- NEWSLETTER -->
    <section class="bg-[#0b0f1a] py-28 text-center">
      <h2 class="text-4xl font-bold mb-6 text-white">Vòng Tròn Nhà Sưu Tầm</h2>

      <p class="max-w-xl mx-auto text-gray-600 mb-8 text-white">
        Thành viên đăng ký sẽ được ưu tiên tiếp cận các phiên bản giới hạn.
      </p>

      <div class="flex justify-center text-white">
        <input
          v-model="email"
          placeholder="Địa chỉ email của bạn"
          class="border p-4 w-80 focus:outline-none"
        />

        <button @click="submit" class="bg-yellow-400 px-8 py-4">
          Tham gia
        </button>
      </div>
    </section>

    <!-- FOOTER -->
    <!-- <footer class="bg-gray-900 text-gray-400 py-16 text-center">
      <h3 class="text-white font-bold mb-6">HOROLOGIST</h3>

      <div class="flex justify-center gap-8 text-sm mb-6">
        <a v-for="link in footer" :key="link">{{ link }}</a>
      </div>

      <p class="text-xs opacity-60">© 2024 The Digital Horologist</p>
    </footer> -->
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";

onMounted(() => {
  AOS.init({
    disable: function () {
      return window.innerWidth < 768; // mobile thì tắt
    },
  });
});

const email = ref("");

const submit = () => {
  alert("Subscribed: " + email.value);
  email.value = "";
};

const links = ["Sản phẩm ", "Tay nghề", "lịch sử", "Kho lưu trữ"];

const collections = [
  {
    title: "Thiết Kế Kiến Trúc Mạnh Mẽ",
    desc: "Triết lý đồng hồ thể thao hiện đại",
    image: "/img/82d77da87b578e9eec561a69b45d3922.jpg",
  },
  {
    title: "Biến Chứng Thiên Văn ",
    desc: "Lấy cảm hứng từ chuyển động mặt trăng",
    image: "/img/4.jpg",
  },
  {
    title: "Di Sản Vàng  ",
    desc: "Kiệt tác đồng hồ sang trọng cổ điển",
    image: "/img/8edcaab69c45b6143e5953268c85d5c8.jpg",
  },
  {
    title: "Cơ Khí Tinh Xảo",
    desc: "Nghệ thuật chế tác đỉnh cao",
    image: "/img/1008579ac17bf048e8cfbce6a4be9bcf.jpg",
  },
  {
    title: "Tinh Hoa Vàng Khối  ",
    desc: "Biểu tượng của đẳng cấp và quyền lực",
    image: "/img/51805732b6c22b4c41c3e5bc08cb230c.jpg",
  },
];

const craft = [
  "Bộ máy hoàn thiện thủ công",
  "Hợp kim chế tác độc quyền",
  "Kiểm định nghiêm ngặt hơn 1000 giờ",
];

const products = [
  {
    name: "Spectre Bạc",
    detail: "Bộ máy tự động • 40mm",
    price: "8.400 USD",
    image: "/img/1.jpg",
  },
  {
    name: "Obsidian Edge",
    detail: "Bộ máy tự động • 44mm",
    price: "$12.200 USD",
    image: "/img/2.jpg",
  },
  {
    name: "Rose Gold Era",
    detail: "Cơ chế lên cót tay • 38mm",
    price: "$18.900 USD",
    image: "/img/3.jpg",
  },
  {
    name: "Rose Gold Era",
    detail: "Manual • 38mm",
    price: "$18900",
    image: "/img/4.jpg",
  },
];
</script>
