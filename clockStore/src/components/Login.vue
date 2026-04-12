<template>
  <div class="min-h-screen flex">
    <!-- LEFT IMAGE -->
    <div class="w-1/2 relative hidden md:block">
      <img
        src="/img/1008579ac17bf048e8cfbce6a4be9bcf.jpg"
        class="absolute inset-0 w-full h-full object-cover"
      />

      <!-- Overlay -->
      <div class="absolute inset-0 bg-black/40"></div>

      <!-- Text -->
      <div class="absolute bottom-16 left-10 text-white max-w-md">
        <p class="text-xs uppercase tracking-widest mb-2 text-yellow-400">
          Since 1892
        </p>

        <h1 class="text-4xl font-serif leading-tight">
          Mastering the <br />
          Complications of Time.
        </h1>

        <div class="w-10 h-[2px] bg-yellow-400 mt-4"></div>
      </div>
    </div>

    <!-- RIGHT FORM -->
    <div class="w-full md:w-1/2 flex items-center justify-center px-8">
      <div class="w-full max-w-md">
        <!-- Title -->
        <h2 class="text-3xl font-serif mb-2">The Archive Access</h2>
        <p class="text-gray-500 mb-8">
          Enter your credentials to manage your collection.
        </p>

        <!-- Email -->
        <div class="mb-6">
          <label class="text-xs uppercase text-gray-400">
            Email Identity
          </label>
          <input
            type="email"
            placeholder="clarence@prestige.com"
            class="w-full border-b py-2 outline-none focus:border-black"
          />
        </div>

        <!-- Password -->
        <div class="mb-6">
          <div class="flex justify-between text-xs text-gray-400">
            <span>Security Key</span>
            <span class="cursor-pointer hover:underline text-gray-500">
              Forgotten your password?
            </span>
          </div>

          <input
            type="password"
            placeholder="••••••••"
            class="w-full border-b py-2 outline-none focus:border-black"
          />
        </div>

        <!-- Button -->
        <button
          class="w-full bg-yellow-500 text-black py-3 uppercase text-sm tracking-wide hover:bg-yellow-400 transition"
        >
          Authenticate →
        </button>

        <!-- Divider -->
        <div class="text-center text-gray-400 text-xs my-6">
          OR CONNECT WITH
        </div>

        <!-- Social -->
        <div class="grid grid-cols-2 gap-4">
          <button class="border py-3 text-sm">Google</button>
          <button class="border py-3 text-sm">Apple ID</button>
        </div>

        <!-- Footer -->
        <div class="flex justify-between mt-8 text-xs text-gray-400">
          <span>New to the Maison?</span>
          <span class="text-yellow-500 cursor-pointer">
            Request an account
          </span>
        </div>
      </div>
    </div>
  </div>
</template>
