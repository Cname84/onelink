<template>
  <div class="h-screen flex flex-col bg-slate-100">
    <div class="flex-1 grid grid-cols-3">
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
        <button
          @click="prefillDemoData"
          class="h-12 flex items-center space-x-2 px-4 border-b text-sm font-medium bg-blue-500 text-white hover:bg-blue-600 rounded"
        >
          <span>Demonstration</span>
          <icon name="mdi:code-json" class="h-4 w-4"></icon>
        </button>
        <a
          href="https://t.me/OxSocial"
          target="_blank"
          class="h-12 flex items-center space-x-2 px-4 border-b text-sm font-medium bg-white text-slate-700 hover:bg-gray-100 rounded"
        >
          <span>Telegram</span>
          <icon name="ph:paper-plane-tilt-bold" class="h-4 w-4"></icon>
        </a>
      </div>
    </div>
    <app-form-preview :data="data" class="p-8"></app-form-preview>
    <a
      href="https://twitter.com/0xsocialETH"
      target="_blank"
      class="absolute bottom-0 right-0 bg-white rounded-tl-lg shadow px-4 py-1 font-medium text-sm text-gray-500"
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


