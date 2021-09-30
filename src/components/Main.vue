<template>
  <div class="main_wrap">

    <div class="main_container container">

      <div class="row" v-if="visible">

        <div class="d-flex justify-content-center mb-5">
          <label for="genre" class="label_style">Choose a music genre:</label>
                <select name="genre" id="genre" v-model="selectedGenre">
                  <option value="" selected></option>
                  <option value="Metal">Metal</option>
                  <option value="Rock">Rock</option>
                  <option value="Pop">Pop</option>
                  <option value="Jazz">Jazz</option>

                </select>
        </div>

        <div v-for="(element, index) in filterGenre" :key="index" class="col-2 card">
          <Card :album="element"/>
        </div>  
      </div>

      <div v-else>
        <Loader />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';
import Loader from './Loader.vue';

export default {
  name: 'Main',
  props: {
    
  },

  components : {
    Card,
    Loader
  },

  data : function () {
    return {
      albumList : [],
      visible : false,
      selectedGenre : ''
    }
  },

  computed: {
    filterGenre: function(){
            let genreDivision = this.albumList.filter((input) => { 
              if (this.selectedGenre != '') {
                return input.genre==this.selectedGenre
              } else {
                return true
              }
              
              
            });
            return genreDivision
            
        }
  }, 

  created : function () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res => {
      this.albumList = res.data.response.slice();
      
      setTimeout(() => {this.visible = true;},
      3500)
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
  height: 200vh;
}

.main_container {
  padding: 50px 0 50px 50px;
  
}

.card {
  margin: 10px;
  background-color: $cardColor;
  border: none;
  }

.label_style {
  color: $whiteColor;
  font-weight: bold;
  margin-right: 20px;
}

</style>
