<template>
  <div class="header_wrap">
      <img src="../assets/img/logo-small.svg" alt="logo Spotify" class="logo_spotify">
  </div>
</template>

<script>
export default {
name : 'Header',
}
</script>

<style lang="scss" scoped>

@import "../style/variables.scss";
@import "../style/general.scss";

.header_wrap {
    background-color: $cardColor;
    height: 50px;
}

.logo_spotify {
    height: 30px;
    margin: 10px 0 10px 20px;
}

</style>