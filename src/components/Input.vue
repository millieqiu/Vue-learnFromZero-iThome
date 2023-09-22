<template>
  <input
  type="text"
  :value="modelValue"
  @input="$emit('update:modelValue', $event.target.value)" />
</template>

<script>
// 元件可以自動傳出資料給上層
export default {
  name: 'myInput',
  props: {
    modelValue: String, // modelValue 為系統名稱，不能自由命名
  },
};
</script>