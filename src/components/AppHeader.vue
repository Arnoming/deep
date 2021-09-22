<template>
  <header class="navbar">
    <h1>
      <!-- <img :src="logoSrc" alt=".." class="img-logo"> -->
      <span>Deep</span>
    </h1>
  </header>
</template>

<script>
export default {
  name:"AppHeader",
  data: function() {
    return {
      logoSrc: require("./../assets/images/deep.png")
    }
  }
}
</script>

<style scoped>
header {
  text-align: center;
}
.navbar {
  height: 80px;
  margin:0 auto;
}

.navbar h1 {
  color: rgb(218, 218, 218);
  padding-top: 20px;
  padding-bottom: 20px;
  letter-spacing: 10px;
  font-family: "Courier New", Courier, monospace;
  font-size: 65px;
}

.img-logo {
  width: 55px;
  margin-right: 20px;
}

</style>