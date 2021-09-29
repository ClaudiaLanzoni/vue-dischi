<template>
    <div class="loader_bg">
        <div class="loader_wrap d-flex justify-content-center align-items-center">

            <img src="../assets/img/horn-icon.png" alt="horns gesture" class="slide">

        </div>
    </div>
</template>

<script>
export default {
    name: 'Loader',

}
</script>

<style lang="scss" scoped>

@import "../style/variables.scss";
@import "../style/general.scss";

.loader_bg {
    background-color: $mainBgColor;
}

.loader_wrap {
  height: 100vh;
}

.slide {
    animation-duration: 2s;
    animation-name: slidein;
    animation-iteration-count: infinite;
}

@keyframes slidein {
  from {
    margin-left: 100%;
    width: 90%;
  }

  to {
    margin-left: 0%;
    width: 50%;
  }
}
</style>