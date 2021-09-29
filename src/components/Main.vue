<template>
  <div class="main_wrap">
    <div class="main_container container">
      <div class="row">
        <div v-for="(element, index) in albumList" :key="index" class="col-2 card">
          <Card :album="element"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';

export default {
  name: 'Main',
  props: {
    
  },

  components : {
    Card
  },

  data : function () {
    return {
      albumList : []
    }
  },

  created : function () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res => {
      this.albumList = res.data.response.slice();
      console.log(this.albumList)
      //console.log(res.data);
  });
  }
}
</script>

<style lang="scss" scoped >

@import "../style/variables.scss";
@import "../style/general.scss";

.main_wrap {
  background-color: $mainBgColor;
}

.main_container {
  padding: 50px 0 50px 50px;
  
}

.card {
  
  margin: 10px;
  background-color: $cardColor;
  border: none;
  }


</style>
