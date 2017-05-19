<template>
  <div class="myitunes">
      <div v-for='prop in song'>
          <img :src="prop.artworkUrl100" alt="" height="200px">
          <marquee><h1>{{prop.artistName}}</h1></marquee>
          <audio controls>
            <source :src="prop.previewUrl" type="audio/ogg">
            <source :src="prop.previewUrl" type="audio/mpeg">
          </audio>
        </div>
        <button @click="getTrack">See Playlist</button>
  </div>
</template>

<script>
import mytunes from '../services/mytunes-service'
export default {
  name: 'myitunes',
  data () {
    return {
      song: {}
    }
  },
  methods:{
    getTrack(){
      this.song = mytunes.getTracks()
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
