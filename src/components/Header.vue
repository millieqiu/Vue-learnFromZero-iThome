<template>
  <h1>This is a Component</h1>
  {{ date }}, {{ greetings }}
</template>


<script>
export default {
  name: 'myHeader',
  props: ['greetings', 'date'], // props 表示可以接收外部資料
};
</script>