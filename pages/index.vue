<template>
  <div class="container">
    <header class="header">
      <h1 class="title">Welcome to 0xSocial</h1>
      <p class="subtitle">0xSocial is revolutionizing social profile creations.</p>
    </header>
    <div class="grid grid-cols-3 divide-x">
      <div class="col-span-2 flex flex-col bg-slate-100">
        <div class="overflow-y-auto p-8">
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
          <button
            @click="prefillDemoData"
            class="button button-primary"
          >
            Add demo data
          </button>
          <div>
            <button
              v-if="clipboardSupported"
              @click="publish"
              class="button button-primary"
            >
              Publish
            </button>
            <a
              href="https://t.me/OxSocial"
              target="_blank"
              class="button button-secondary"
            >
              Telegram
            </a>
          </div>
        </div>
      </div>
      <app-form-preview :data="data" />
    </div>
    <a
      href="https://twitter.com/0xsocialETH"
      target="_blank"
      class="attribution"
    >
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
  // ...demo data setup...
};

const clipboardSupported = "navigator" in window && "clipboard" in navigator;

const publish = () => {
  // ...publish logic...
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

.grid {
  gap: 1rem;
  flex-grow: 1;
}

.header {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 2rem;
  text-align: center;
}

.title {
  font-size: 2rem;
  font-weight: bold;
  color: #1a202c;
}

.subtitle {
  font-size: 1.25rem;
  color: #4a5568;
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
  color: #fff;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

.button-primary {
  background-color: #4c51bf;
}

.button-primary:hover {
  background-color: #434190;
}

.button-secondary {
  background-color: #cbd5e0;
  color: #1a202c;
}

.button-secondary:hover {
  background-color: #a0aec0;
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
