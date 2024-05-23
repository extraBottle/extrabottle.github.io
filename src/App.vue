<template>
  <router-view />
</template>

<script setup>
import { stopLoading } from './utils/loading'
import { popupFail } from './utils/popup'
import { useRouter } from 'vue-router';
import { onErrorCaptured } from 'vue';
defineOptions({
  name: 'App'
});

// 오류 발생시 메인화면으로 보냄
const router = useRouter()
onErrorCaptured(()=>{
  stopLoading()
  router.push('/')
  popupFail('오류가 발생했습니다')
})

</script>
