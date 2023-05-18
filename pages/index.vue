<template>
  <div class="h-screen flex flex-col">
    <div class="h-1/4 bg-gradient-to-b from-blue-500 to-blue-700 text-white">
      <div class="flex flex-col justify-center h-full px-8">
        <h1 class="text-4xl font-bold mb-4">Welcome to 0xSocial</h1>
        <p class="text-lg mb-8">Seamless social profile creations.</p>
        <a
          href="https://example.com"
          target="_blank"
          class="py-2 px-6 bg-white text-blue-500 rounded-full font-medium text-lg shadow hover:bg-blue-100"
        >
          Get Started
        </a>
      </div>
    </div>
    <div class="flex-1 grid grid-cols-3 bg-slate-100">
      <div class="col-span-2 flex">
        <div class="overflow-y-auto p-8">
          <app-form-profile
            v-model:name="data.n"
            v-model:desc="data.d"
            v-model:image="data.i"
          ></app-form-profile>
          <app-form-hr></app-form-hr>
          <app-form-social-links
            v-model:twitter="data.t"
            v-model:telegram="data.tg"
            v-model:discord="data.d"
            v-model:email="data.e"
            v-model:youtube="data.y"
          ></app-form-social-links>
          <app-form-hr></app-form-hr>
          <app-form-links v-model="data.ls"></app-form-links>
        </div>
      </div>
      <div class="col-span-1 border-t bg-white flex flex-col items-center justify-center">
        <a
          href="https://t.me/OxSocial"
          target="_blank"
          class="h-12 flex items-center space-x-2 px-4 border-b text-xs font-medium bg-white text-slate-700"
        >
          <span>Telegram</span>
          <icon name="ph:paper-plane-tilt-bold" class="h-4 w-4"></icon>
        </a>
      </div>
    </div>
    <app-form-preview :data="data"></app-form-preview>
    <a
      href="https://twitter.com/0xsocialETH"
      target="_blank"
      class="bg-white rounded-tl-lg shadow px-4 py-1 font-medium text-sm text-gray-500 self-end"
    >
      Made by 0xSocial
    </a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: {
        n: '',
        d: '',
        i: '',
        t: '',
        tg: '',
        discord: '',
        e: '',
        y: '',
        ls: []
      }
    };
  }
};
</script>


