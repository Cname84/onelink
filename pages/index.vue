<template>
  <div class="container">
    <div class="hero">
      <h1 class="hero-title">Welcome to 0xSocial</h1>
      <p class="hero-subtitle">0xSocial is revolutionizing social profile creations.</p>
      <button class="scroll-button" @click="scrollToContent">Scroll Down</button>
    </div>
    <div class="grid grid-cols-3 divide-x">
      <div class="col-span-2 flex flex-col bg-slate-100">
        <div class="overflow-y-auto p-8">
          <h1>Welcome to 0xSocial</h1>
          <p>0xSocial is revolutionizing social profile creations.</p>

          <!-- Rest of the code -->

        </div>
        <div class="border-t bg-white flex items-center justify-between">
          <!-- Buttons at the top of the screen -->
          <div class="top-buttons">
            <button @click="prefillDemoData" class="button">Add demo data</button>
            <button v-if="clipboardSupported" @click="publish" class="button">Publish</button>
            <a href="https://t.me/OxSocial" target="_blank" class="button">Telegram</a>
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
// Rest of the code remains the same
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

.scroll-button {
  background-color: #374151;
  color: #fff;
  border: none;
  padding: 0.75rem 1rem;
  font-size: 1rem;
  font-weight: 500;
  cursor: pointer;
}

.grid {
  gap: 1rem;
  flex-grow: 1;
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

.top-buttons {
  display: flex;
  gap: 1rem;
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

