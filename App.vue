<script setup>
import { ref } from 'vue';

// 1. Variabel reaktif dengan ref
const message = ref('Halo, Everyone!');

// 2. Text interpolation
const name = ref('I am Nazwa');

// 3. Form Binding
const inputText = ref('');

// 4. Event Listener
const count = ref(0);

// 5. Attribute Binding
const url = ref('https://vuejs.org');

// 6. Conditional Rendering
const isVisible = ref(true);
</script>

<template>
  <!-- Variabel Reaktif -->
  <h1 class="title">{{ message }}</h1>

  <!-- Text Interpolation -->
  <p class="greeting">Halo, <span>{{ name }}</span>!</p>

  <!-- Form Binding -->
  <div class="section">
    <input v-model="inputText" placeholder="Ketik sesuatu..." class="input-box" />
    <p>Sedang mengetik: <strong>{{ inputText }}</strong></p>
  </div>

  <!-- Event Listener -->
  <div class="section">
    <button @click="count++" class="btn">Klik ini!</button>
    <p>Jumlah klik: <strong>{{ count }}</strong></p>
  </div>

  <!-- Attribute Binding -->
  <div class="section">
    <a :href="url" target="_blank" class="link">Kunjungi Vue.js</a>
  </div>

  <!-- Conditional Rendering -->
  <div class="section">
    <button @click="isVisible = !isVisible" class="btn toggle">
      Sembunyikan Teks
    </button>
    <p v-if="isVisible" class="fade-in">Teks ini bisa disembunyikan.</p>
  </div>
</template>

<style scoped>
/* Judul */
.title {
  text-align: center;
  font-size: 90px;
  color: #527191;
  margin-bottom: 90px;
}

/* Text Interpolation */
.greeting {
  text-align: center;
  font-size: 20px;
  margin-bottom: 15px;
}

.greeting span {
  font-weight: bold;
  color: #527191;
}

/* Section Styling */
.section {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 15px;
}

/* Input */
.input-box {
  width: 65%;
  padding: 9px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
}

/* Buttons */
.btn {
  padding: 10px 15px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: #52729181;
  color: white;
  transition: background 0.3s ease;
  margin: 5px;
}

.btn:hover {
  background-color: #527191;
}

/* Toggle button */
.toggle {
  background-color: #52729193;
}

.toggle:hover {
  background-color: #527191;
}

/* Links */
.link {
  text-decoration: none;
  font-size: 16px;
  color: #fbff00;
  font-weight: bold;
}

.link:hover {
  text-decoration: underline;
}

/* Fade in effect */
.fade-in {
  animation: fadeIn 0.5s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
