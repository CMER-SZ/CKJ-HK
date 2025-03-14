<template>
  <div>
    <Head>
      <Title>{{ error.statusCode === 500 ? 'CKJ愛康健齒科連鎖 | 香港官方網站 | 長者醫療券大灣區試點' : '页面错误' }}</Title>
    </Head>
    <h1 v-if="error.statusCode === 500">CKJ愛康健齒科連鎖 | 香港官方網站 | 長者醫療券大灣區試點</h1>
    <h1 v-else>CKJ愛康健齒科連鎖 | 香港官方網站 | 長者醫療券大灣區試點</h1>
  </div>
</template>

<script setup>
defineProps({
  error: Object
});
</script>
