<template>
  <button @click="show('tab1')">Component1</button>
  <button @click="show('tab2')">Component2</button>
  <button @click="show('tab3')">Component3</button>

  <!-- 使用 v-if 來決定當切換到 tab 時應出現各自對應的內容（元件） -->
  <ComponentOne v-if="tab === 'tab1'"/>
  <ComponentTwo v-if="tab === 'tab2'"/>
  <keep-alive>
    <ComponentThree v-if="tab === 'tab3'" />
  </keep-alive>
</template>

<script>
import ComponentOne from './components/Component1.vue';
import ComponentTwo from './components/Component2.vue';
import ComponentThree from './components/Component3.vue';

export default {
  name: 'App',
  components: {
    ComponentOne,
    ComponentTwo,
    ComponentThree,
  },
  data() {
    return {
      tab: 'tab1',
    };
  },
  methods: {
    show(index) {
      this.tab = index;
    },
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
