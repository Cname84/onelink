<template>
  <div class="container">
    <div class="hero">
      <h1 class="hero-title">Welcome to 0xSocial</h1>
      <p class="hero-subtitle">0xSocial is revolutionizing social profile creations.</p>
      <div class="hero-buttons">
        <button @click="prefillDemoData" class="button">
          Add demo data
        </button>
        <div>
          <button v-if="clipboardSupported" @click="publish" class="button">
            Publish
          </button>
          <a href="https://t.me/OxSocial" target="_blank" class="button">
            <img src="https://e1.pxfuel.com/desktop-wallpaper/700/536/desktop-wallpaper-telegram-logo-png-transparent-telegram-logo-png-telegram-icon.jpg" alt="Telegram" class="social-icon" />
          </a>
        </div>
      </div>
    </div>
    <div class="grid grid-cols-3 divide-x">
      <div class="col-span-2 flex flex-col bg-slate-100">
        <div class="overflow-y-auto p-8">
          <h1>Welcome to 0xSocial</h1>
          <p>0xSocial is revolutionizing social profile creations.</p>

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
          />
          <app-form-hr />
          <app-form-links v-model="data.ls" />
        </div>
        <div class="border-t bg-white flex items-center justify-between">
          <button @click="prefillDemoData" class="button">
            Add demo data
          </button>
          <div>
            <button v-if="clipboardSupported" @click="publish" class="button">
              Publish
            </button>
            <a href="https://t.me/OxSocial" target="_blank" class="button">
              <img src="telegram.png" alt="Telegram" class="social-icon" />
            </a>
          </div>
        </div>
      </div>
      <app-form-preview :data="data" />
    </div>
    <a href="https://twitter.com/0xsocialETH" target="_blank" class="attribution">
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
    i:
      "https://c.ndtvimg.com/2023-01/e3p66s1o_elon-musk-afp-650_650x400_26_January_23.jpg?im=Resize=(1230,900)",
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

const clipboardSupported = "navigator" in globalThis && "clipboard" in navigator;

const publish = () => {
  const url = `${location.protocol}//${location.host}/1?data=${encodeData(data.value)}`;
  if (clipboardSupported) {
    navigator.clipboard.writeText(url).then(() => {
      alert("Link copied to clipboard");
    });
  }
};
</script>

<style scoped>
.container {
  margin: 0 auto;
  max-width: 960px;
  padding: 1rem;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.hero {
  background-color: #f2f2f2;
  padding: 2rem;
  margin-bottom: 2rem;
  text-align: center;
}

.hero-title {
  font-size: 2rem;
  font-weight: bold;
  color: #333;
  margin-bottom: 0.5rem;
}

.hero-subtitle {
  font-size: 1.25rem;
  color: #666;
}

.hero-buttons {
  display: flex;
  justify-content: center;
  margin-top: 1rem;
}

.button {
  height: 3rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.5rem 1rem;
  border: 1px solid #ccc;
  font-size: 0.875rem;
  font-weight: 500;
  background-color: #fff;
  color: #374151;
  cursor: pointer;
}

.social-icon {
  width: 1.5rem;
  height: 1.5rem;
}

.grid {
  gap: 1rem;
  flex-grow: 1;
}

.attribution {
  margin-top: auto;
  background-color: #fff;
  border-radius: 0.375rem 0 0 0;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 0.25rem 0.5rem;
  font-size: 0.875rem;
  font-weight: 500;
  color: #9ca3af;
  text-decoration: none;
}
</style>

