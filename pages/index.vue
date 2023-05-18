<template>
  <div class="h-screen grid grid-cols-3 divide-x">
    <div class="col-span-2 h-screen flex flex-col bg-slate-100">
      <div class="flex-1 overflow-y-auto p-8">
        <app-form-profile
          v-model:name="data.n"
          v-model:desc="data.d"
          v-model:image="data.i"
        />
        <app-form-hr />
        <app-form-social-links
          v-model:facebook="data.f"
          v-model:twitter="data.t"
          v-model:instagram="data.ig"
          v-model:github="data.gh"
          v-model:telegram="data.tg"
          v-model:linkedin="data.l"
          v-model:email="data.e"
          v-model:whatsapp="data.w"
          v-model:youtube="data.y"
      <div class="border-t bg-white flex items-center">
  <button
    @click="prefillDemoData"
    class="h-12 flex items-center space-x-2 px-4 border-r text-xs font-medium bg-white text-slate-700"
  >
    <span> Add demo data </span>
    <icon name="mdi:code-json" class="h-4 w-4" />
  </button>
  <a
    href="https://t.me/OxSocial"
    target="_blank"
    class="h-12 flex items-center space-x-2 px-4 border-r text-xs font-medium bg-white text-slate-700"
  >
    <span>Telegram</span>
    <icon name="ph:paper-plane-tilt-bold" class="h-4 w-4" />
  </a>
  <button
    @click="customButtonAction"
    class="h-12 flex items-center space-x-2 px-4 border-r text-xs font-medium bg-white text-slate-700"
  >
    <span>Custom Button</span>
    <icon name="mdi:star" class="h-4 w-4" />
  </button>
  <a
    href="https://example.com"
    target="_blank"
    class="h-12 flex items-center space-x-2 px-4 border-r text-xs font-medium bg-white text-slate-700"
  >
    <span>Custom Link Button</span>
    <icon name="mdi:link" class="h-4 w-4" />
  </a>
</div>

      Made by 0xSocial 
    </a>
  </div>
</template>

<script setup>
import { encodeData } from "../utils/transformer";
import { ref } from "vue";

const data = ref({
  n: "",
  d: "",
  i: "",
  f: "",
  t: "",
  ig: "",
  gh: "",
  tg: "",
  l: "",
  e: "",
  w: "",
  y: "",
  ls: [],
});

const prefillDemoData = () => {
  data.value = {
    n: "Elon Musk",
    d: "I’m Elon Musk, the richest person on earth. Also a pro memer.",
    i: "https://upload.wikimedia.org/wikipedia/commons/3/34/Elon_Musk_Royal_Society_%28crop2%29.jpg",
    f: "https://www.facebook.com/john_snow",
    t: "https://twitter.com/john_snow",
    ig: "https://www.instagram.com/john_snow",
    e: "mail@john_snow.cc",
    gh: "https://github.com/john_snow",
    tg: "https://t.me/john_snow",
    w: "+918888888888",
    y: "https://youtube.com/@john_snow",
    l: "https://linkedin.com/john_snow",
    ls: [
      {
        l: "My Website",
        i: "ph:globe-duotone",
        u: "https://example.com",
      },
      {
        l: "Amazon wishlist",
        i: "ant-design:amazon-outlined",
        u: "https://amazon.in",
      },
      {
        l: "React JS course",
        i: "grommet-icons:reactjs",
        u: "https://reactjs.org/",
      },
      {
        l: "Donate for our cause",
        i: "iconoir:donate",
        u: "https://who.int",
      },
      {
        l: "Download my resume",
        i: "ph:file-pdf",
        u: "https://google.com",
      },
    ],
  };
};

const publish = () => {
  const url = `${window.location.origin}/1?data=${encodeData(data.value)}`;
  navigator.clipboard.writeText(url).then(() => {
    alert("Link copied to clipboard");
  });
};
</script>
