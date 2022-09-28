<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  created() {
    document.title = "拉布拉马";
  },
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    font-family: "PingFang";
    user-select: none;
  }

  html, body{
    width: 100vw;
    height: 100vh;
  }

  @font-face {
    font-family: "PingFang";
    src: url("@/assets/font/pingfang.ttf");
  }

  ::-webkit-scrollbar{
    width: 10px;
  }

  ::-webkit-scrollbar-thumb{
    width: 10px;
    border-radius: 5px;
    background-color: rgba(0, 0, 0 ,0.2);
  }
</style>