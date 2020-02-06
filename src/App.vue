<template>
  <div id="app">
    <PhotographersList 
      v-bind:photographers="photographers"
      v-on:radioOnPhotographer="fetchAlbums"
    />
    <AlbumsList 
      v-bind:albums="albums"
      v-on:radioOnAlbum="fetchPictures"
    /> 
    <PicturesList 
      v-bind:pictures="pictures"
    />

  </div>
</template>

<script>
import PhotographersList from '@/components/PhotographersList'
import AlbumsList from '@/components/AlbumsList'
import PicturesList from '@/components/PicturesList'
export default {
  name: 'app',
  data() {
    return {
      photographers: [],
      albums: [],
      pictures: []
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(response => response.json())
      .then(data => this.photographers = data)
  },
  components: {
    PhotographersList, AlbumsList, PicturesList
  },
  methods: {
    fetchAlbums(id) {
      let url = 'https://jsonplaceholder.typicode.com/albums/?userId=' + id
      console.log(id, url)

      fetch(url)
        .then(response => response.json())
        .then(data => this.albums = data)
    },
    fetchPictures(id) {
      let url = 'https://jsonplaceholder.typicode.com/photos?albumId=' + id
      console.log(id, url)

      fetch(url)
        .then(response => response.json())
        .then(data => this.pictures = data)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
