<template>
  <HeaderV2 />
  <div class="SuccessfulBox">
    <div class="success-container">
      <img
        src="https://statichk.cmermedical.com/cph-hk/Successful.avif"
        alt="成功图标"
        class="success-icon"
      />
      <h1 class="success-title">提交成功！</h1>
      <p class="success-message">
        感謝您提交表單，我們將於10小時內與您聯繫，謝謝！
      </p>
      <button class="back-button" @click="goBack()">返回上一頁</button>
      <p class="timer">
        <span>{{ timeLeft }}</span> 秒後自動返回上一頁
      </p>
    </div>
  </div>
  <!-- <PageFooter /> -->
  <FooterV2 />
  <!-- <PageNewNavbarSide v-if="windowWidth > 768" />
    <PageNavbar v-else /> -->
  <AsideV2 />
</template>
<script setup>
import { ref, onMounted } from 'vue'

let timeLeft = ref(5)

function countdown() {
  const timer = setInterval(() => {
    timeLeft.value--
    if (timeLeft.value <= 0) {
      clearInterval(timer)
      goBack()
    }
  }, 1000)
}

function goBack() {
  window.history.back()
}

onMounted(() => {
  countdown()
})
</script>
<style lang="scss" scoped>
.SuccessfulBox {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
    'Helvetica Neue', Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  /* min-height: 100vh; */
  padding-top: 150px;
  padding-bottom: 100px;
}

.success-container {
  background: white;
  padding: clamp(20px, 5vw, 40px);
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: min(90%, 400px);
  margin: 16px;
}

.success-icon {
  width: clamp(60px, 15vw, 80px);
  height: clamp(60px, 15vw, 80px);
  margin-bottom: clamp(16px, 4vw, 24px);
}

.success-title {
  color: #52c41a;
  font-size: clamp(20px, 5vw, 24px);
  margin-bottom: clamp(12px, 3vw, 16px);
  word-break: break-word;
}

.success-message {
  color: #666;
  margin-bottom: clamp(24px, 6vw, 32px);
  line-height: 1.6;
  font-size: clamp(14px, 4vw, 16px);
  padding: 0 clamp(10px, 2.5vw, 20px);
}

.back-button {
  background: #52c41a;
  color: white;
  border: none;
  padding: clamp(10px, 2.5vw, 12px) clamp(24px, 6vw, 32px);
  border-radius: 6px;
  font-size: clamp(14px, 4vw, 16px);
  cursor: pointer;
  transition: background 0.3s;
  width: fit-content;
  min-width: 120px;
}

.back-button:hover {
  background: #49ad17;
}

.timer {
  color: #999;
  font-size: clamp(12px, 3.5vw, 14px);
  margin-top: clamp(12px, 3vw, 16px);
}

/* 移动端适配 */
@media screen and (max-width: 360px) {
  .success-container {
    padding: 16px;
    margin: 12px;
  }

  .success-icon {
    width: 50px;
    height: 50px;
    margin-bottom: 12px;
  }

  .success-title {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .success-message {
    font-size: 13px;
    margin-bottom: 20px;
    padding: 0 8px;
  }

  .back-button {
    padding: 8px 20px;
    font-size: 13px;
    min-width: 100px;
  }

  .timer {
    font-size: 11px;
    margin-top: 10px;
  }
}

/* 超小屏幕适配 */
@media screen and (max-width: 320px) {
  .success-container {
    padding: 12px;
    margin: 8px;
  }

  .success-icon {
    width: 45px;
    height: 45px;
    margin-bottom: 10px;
  }

  .success-title {
    font-size: 16px;
    margin-bottom: 8px;
  }

  .success-message {
    font-size: 12px;
    margin-bottom: 16px;
    padding: 0 6px;
  }

  .back-button {
    padding: 7px 16px;
    font-size: 12px;
    min-width: 90px;
  }

  .timer {
    font-size: 10px;
    margin-top: 8px;
  }
}
</style>