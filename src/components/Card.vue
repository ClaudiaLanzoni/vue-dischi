<template>
        <div class="card">
            <img :src="album.poster" :alt="album.author" class="p-2">
            <div class="album_style">{{album.title}}</div>
            <p>{{album.author}}</p>
            <p>{{album.year}}</p>
        </div>
</template>

<script>
export default {
    name : 'Card',
    props : {
        album : Object
    },

    
}
</script>



<style lang="scss" scoped>

@import "../style/variables.scss";
@import "../style/general.scss";

.card {
    font-style: $bodyFont;

    p {
        color: $artistColor;
        text-align: center;
    }
}

.album_style {
    color: $whiteColor;
        text-transform: uppercase;
        font-weight: bold;
        text-align: center;
        margin-bottom: 10px;
}

</style>