<template>
  <div>
    <v-layout>
      <v-flex xs6>
        <song-metadata :song="song" />
      </v-flex>

      <v-flex xs6 class="ml-2">
        <you-tube :youtubeId="song.youtubeId" />
      </v-flex>
    </v-layout>
    <v-layout class="mt-2 mb-5">
      <v-flex xs6>
        <lyrics :song="song" />
      </v-flex>
      <v-flex xs6 class="ml-2">
        <tab :song="song" />
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import SongMetadata from '@/components/ViewSong/SongMetadata'
import Lyrics from '@/components/ViewSong/Lyrics'
import Tab from '@/components/ViewSong/Tab'
import YouTube from '@/components/ViewSong/YouTube'
import SongsService from '@/services/SongsService'
import Panel from '@/components/Panel'
export default {
  data () {
    return {
      song: {}
    }
  },
  async mounted () {
    const songId = this.$store.state.route.params.songId
    this.song = (await SongsService.show(songId)).data
    console.log(this.song)
  },
  components: {
    Panel,
    SongMetadata,
    YouTube,
    Lyrics,
    Tab
  }
}
</script>

<style scoped>
textarea {
  width: 90%;
  font-family: monospace;
  border: none;
  height: 232px;
  border-style: none;
  border-color: transparent;
  overflow: auto;
  padding: 40px;
}
</style>

