<template>
  {{ message }}
</template>

<script>
// 程式邏輯放置的地方

export default { // 所有程式邏輯都要寫在 export default 裡
  name: 'App', // 宣告這個 Vue
  data() {
    return {
      message: 'Hello World',
    }
  },
}
</script>

<style>
/* 相關 css 標籤語法放置的地方 */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
