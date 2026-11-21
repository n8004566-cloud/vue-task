
<script setup>
import { ref } from 'vue'

const colors = [
  '#F8A5C2',
  '#A8DADC',
  '#BDB2FF',
  '#FFD6A5',
  '#CAFFBF',
  '#FFC6FF'
]

const currentColor = ref('#A8DADC')

function changeColor() {
  const randomIndex = Math.floor(Math.random() * colors.length)
  currentColor.value = colors[randomIndex]
}
</script>

<template>
  <div class="page" :style="{ backgroundColor: currentColor }">

    <div class="card">

      <div class="emoji">🎨</div>

      <h1>دنیای رنگ ها</h1>

      <p>با یک کلیک دنیای خودت رو رنگی کن!</p>

      <button @click="changeColor">
        تغییر رنگ صفحه ✨
      </button>

      <div class="color-box">
        <span>رنگ فعلی:</span>
        <span class="color-code">{{ currentColor }}</span>
      </div>

    </div>

    <footer>
    امیدوارم لذت برده باشین
    </footer>

  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.page {
  width: 100%;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: Tahoma, sans-serif;
  transition: background-color 0.5s;
  padding: 20px;
  direction: rtl;
}

.card {
  width: 100%;
  max-width: 500px;
  min-height: 350px;
  background-color: white;
  border-radius: 25px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.12);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 35px 20px;
  text-align: center;
}

.emoji {
  font-size: 60px;
  margin-bottom: 10px;
}

h1 {
  color: #444;
  font-size: 32px;
}

p {
  color: #888;
  font-size: 16px;
  margin-bottom: 30px;
}

button {
  background: #8e7dff;
  color: white;
  border: none;
  padding: 16px 35px;
  border-radius: 12px;
  font-size: 17px;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background: #6c5ce7;
  transform: scale(1.05);
}

.color-box {
  margin-top: 30px;
  color: #555;
  font-size: 15px;
}

.color-code {
  direction: ltr;
  display: inline-block;
  color: #8e7dff;
  font-weight: bold;
  margin-right: 8px;
}

footer {
  margin-top: 30px;
  color: #444;
  font-size: 13px;
}
</style>
