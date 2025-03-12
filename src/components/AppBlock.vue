<template>
  <div class="container">
    <slot name="head"></slot>
    <slot name="cont"></slot>
    <slot name="footer"></slot>
  </div>
</template>
<script></script>
<style>
.container {
  background-color: rgb(48, 46, 46);
  color: white;
  width: 96%;
  height: 100px;
  border-radius: 10px;
  margin: auto;
}
</style>
