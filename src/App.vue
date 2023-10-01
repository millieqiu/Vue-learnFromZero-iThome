<template>
  {{ user.id }} {{ user.name }}
  <hr>
  <button @click="incrementCount()">Click me</button>
  {{ count }}
  <hr>
  <!-- 使用 toRefs -->
  {{ email }}
  <input type="text" v-model="email" />
</template>

<script>
import { ref, reactive, toRefs } from 'vue';

export default {
  name: 'App',
  setup() {
    const user = reactive({
      id: 0,
      name: '',
    });
    const count = ref(0);
    const userData = reactive({
      email: '',
    });

    user.id = 1;
    user.name = 'Allan';

    function incrementCount() {
      count.value++;
    }

    return {
      user,
      count,
      ...toRefs(userData),
      incrementCount,
    };
  },
};
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
