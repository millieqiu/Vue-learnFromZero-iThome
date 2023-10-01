<template>
  <div>
    <!-- 使用 slot 可以讓外部 HTML 傳入 -->
    <slot></slot>
    <!-- 使用 slot name 可以讓外部指定 HTML 傳入 -->
    <slot name="header"></slot>
    <slot name="content"></slot>

    <!-- 設定 component 的 style 會傳遞到父 component -->
    <h3>Style</h3>
  </div>
</template>

<script>
export default {
  name: 'componentInput'
};
</script>

<!-- 設定 component 的 style 會傳遞到父 component -->
<style>
h3 {
  color: red;
}
</style>
