<template>
  <div class="home">
    <!-- YOU WILL PROBABLY END UP WITH SOMETHING LIKE THIS -->
    <itunes class="itunes"></itunes>
    <my-tunes class="my-tunes"></my-tunes>
  </div>
</template>

<script>
import Itunes from './Itunes'
import MyTunes from './MyTunes'


export default {
  name: 'home',
  components: {Itunes, MyTunes},
  data () {
    return {
      
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
