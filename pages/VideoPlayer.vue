<template>
  <div class="video-player">
    <Player :activeVideo="activeVideo" :videos="videos"/>
    <PlayList @choose="chooseVideo" @remove="removeVideo" :videos="videos"/>
  </div>
</template>

<script>
import Player from "../components/Player";
import videos from '../static/dataVideos/videos';

export default {
  name: "VideoPlayer",
  components: {Player},

  data: () => ({
    videos,
    activeVideo: videos[0]

  }),
  methods: {
    chooseVideo(video) {
      this.activeVideo = video;
    },
    removeVideo(video) {
      if (this.videos.length > 1) {
        const videoList = this.videos.filter(value => value !== video)
        this.videos = videoList
        this.activeVideo = this.videos[0]
      }
    }
  }
}
</script>

<style scoped>

.video-player {
  gap: 1rem;
  padding: 20px;
  min-width: 100vw;
}

@media (max-width: 768px) {
  .video-player {
    flex-wrap: wrap
  }
}
</style>
