<template>
  <div class="itunes">
   <form @submit.prevent="search">
            <input type="text" v-model="query">
            <button type="submit">Find</button>
        </form>
        <div v-for='prop in song'>
          <img :src="prop.artworkUrl100" alt="" height="200px">
          <marquee><h1>{{prop.artistName}}</h1></marquee>
          <audio controls>
            <source :src="prop.previewUrl" type="audio/ogg">
            <source :src="prop.previewUrl" type="audio/mpeg">
          </audio>
          <button @click="addSong(prop)">Add</button>
        </div>
        </div>
</template>

<script>
import itune from '../services/itunes-service'
import mytunes from '../services/mytunes-service'

export default {
  name: 'itunes',
  data () {
    return {
      query: '',
      song: {}
    }
  },
   methods: {
    search(){
      itune.getMusicByArtist(this.query).then(songs=>{
          this.song = JSON.parse(songs).results
          console.log(this.song)
      })
    },
      addSong(item){
        mytunes.addTrack(item)
      }
    }
  }

</script>


<style>
/**
* YOU SHOULD PROBABLY MAKE THIS LOOK BETTER :)
* BOOTSTRAP IS FOR THE WEAK FLEXBOX IS KING
* -- McCall
**/
.my-tunes{
  display: inline-block;
  min-height: 500px;
  min-width: 50%;
  background: purple;
}
.itunes{
  display: inline-block;
  background: pink;
  min-height: 500px;
  min-width: 45%;
}
</style>
