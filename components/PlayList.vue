<template>
<section>
  <div v-for="video in videos" :key="video.id">
    <div class="thumbnail-img">
      <div @click="chooseVideo(video)" class="thumbnail">
        <img :src="video.cover"/>
      </div>
    </div>
    <div class="thumbnail-info">
      <h3>{{ video.title }}</h3>
      <p>{{ video.subtitle }}</p>
    </div>

  </div>
</section>
</template>

<script>
export default {
  name: "PlayList",
  props: ['videos', 'activeVideo'],
  data: () => ({
    videoF: this.activeVideo
  }),
  methods: {
    chooseVideo(video) {
      //SET VIDEO AS ACTIVE VIDEO
      this.videoF = video;
      console.log(video)
      // //INCREASE THE VIDEOS VIEWS BY 1
      // video.views += 1;
      console.log(this.videoF)
    }
  }
}
</script>

<style scoped>

</style>
