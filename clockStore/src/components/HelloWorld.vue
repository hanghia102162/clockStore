<template>
  <div class="font-sans bg-[#0b1120] text-gray-800">
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
    <section
      class="p-5 lg:py-24 lg:px-29 bg-[#0b1120] min-w-[100%] max-w-7xl mx-auto"
    >
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
    <section class="bg-[#0b0f1a] min-w-[100%] text-white p-5 lg:py-28">
      <div class="max-w-7xl mx-auto grid md:grid-cols-2 gap-16 items-center">
        <img
          src="/img/56615e3f81e281f4285e08ea7b7182ed.jpg"
          class="grayscale"
        />

        <div>
          <h2 class="text-yellow-400 uppercase tracking-widest mb-4">
            NGHỆ THUẬT CHẾ TÁC THỤY SĨ
          </h2>

          <h3 class="text-4xl md:text-5xl font-bold mb-6">
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
    <section class="py-16 md:py-24 bg-[#0b1120] px-5">
      <div class="max-w-7xl mx-auto md:px-5 md:px-0">
        <!-- TITLE -->
        <div
          class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-10 md:mb-14"
        >
          <div>
            <p
              class="uppercase tracking-[3px] text-yellow-500 text-[10px] md:text-xs mb-2"
            >
              Swiss Collection
            </p>

            <h2 class="text-2xl md:text-5xl font-bold text-white leading-tight">
              Tuyển Chọn Mới Nhất
            </h2>
          </div>

          <button
            class="hidden md:block text-sm text-gray-400 hover:text-yellow-500 transition"
          >
            Xem tất cả →
          </button>
        </div>

        <!-- PRODUCTS -->
        <div
          class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-4 gap-4 md:gap-7"
        >
          <div
            v-for="product in products"
            :key="product.name"
            class="group bg-[#111827] rounded-xl md:rounded-[20px] overflow-hidden border border-white/10 transition-all duration-500 active:scale-[0.98] md:hover:-translate-y-2 md:hover:border-yellow-500/40"
          >
            <!-- IMAGE -->
            <div class="relative overflow-hidden">
              <img
                :src="product.image"
                class="w-full h-[200px] sm:h-[240px] md:h-[320px] object-cover"
              />

              <div
                class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent"
              ></div>

              <span
                class="absolute top-3 left-3 bg-black/40 text-yellow-400 text-[9px] px-2 py-1 rounded-full"
              >
                LIMITED
              </span>
            </div>

            <!-- CONTENT -->
            <div class="p-4 md:p-6">
              <h3 class="text-base md:text-xl font-semibold text-white mb-1">
                {{ product.name }}
              </h3>

              <p class="text-gray-400 text-xs md:text-sm mb-4">
                {{ product.detail }}
              </p>

              <div class="flex items-center justify-between">
                <p class="text-yellow-500 font-bold text-base md:text-2xl">
                  {{ product.price }}
                </p>

                <button
                  class="w-9 h-9 md:w-11 md:h-11 rounded-full border border-white/10 text-white active:scale-95 md:hover:bg-yellow-500 md:hover:text-black transition"
                >
                  →
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- NEWSLETTER -->
    <section class="bg-[#0b0f1a] py-28 text-center px-4">
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
