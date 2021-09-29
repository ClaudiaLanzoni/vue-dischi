<template>
  <div class="card">
      <img :src="album.poster" :alt="album.author">
        <div>{{album.title}}</div>
        <div>{{album.author}}</div>
        <div>{{album.year}}</div>
  </div>
</template>

<script>
export default {
    name : 'Card',
    props : {
        album : Object
    }
}
</script>

<style lang="scss">

@import "../style/variables.scss";
@import "../style/general.scss";

    .card {
    margin: 40px;
    }

</style>