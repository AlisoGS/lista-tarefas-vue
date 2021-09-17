<template>
  <header>
      <h1>{{ valor }}</h1>
  </header>
</template>

<script>
export default {
  props: ["valor"],
};
</script>

<style>
header{
  background-color: #10ac80;
  height: 50px;
  width: 100%;
  display: flex;
  top: 0px;
  justify-content:center;
  color:ghostwhite;
}
</style>