<template>
  <div>
    <input type="text" v-model="text" />
    <button @click="$emit('viewText', text)">Send</button>
  </div>
</template>

<script>
export default {
  name: 'myView',
  emits: ['viewText'], // 使用 emits 將元件的資料傳回父層
  data() {
    return {
      text: '',
    };
  },
};
</script>