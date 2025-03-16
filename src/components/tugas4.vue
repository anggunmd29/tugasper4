<script setup>
import { ref } from 'vue';

const count = ref(0);
const showMessage = ref(true);
const message = ref('Pesan Awal');
const textColor = ref('black');

function increment() {
  count.value++;
  if (count.value > 5) {
    showMessage.value = false;
    message.value = 'Pesan setelah count > 5';
    textColor.value = 'red';
  }
}

function changeMessage() {
  message.value = 'Pesan telah diubah!';
  textColor.value = 'blue';
}
</script>

<template>
  <div>
    <button @click="increment">Tambah Count ({{ count }})</button>
    <button @click="changeMessage">Ubah Pesan</button>
    <h1 :style="{ color: textColor }" v-if="showMessage">{{ message }}</h1>
    <p v-else>Pesan disembunyikan!</p>
  </div>
</template>

