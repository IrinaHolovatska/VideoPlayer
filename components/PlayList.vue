<template>
      <section class="playlist">
        <h3>Now Playing <span> 🎵 </span></h3>
        <ul>
          <li v-for="video in videos" :key="video.id" class="video-list">
            <div class="cover-playlist" @click="chooseVideo(video)">
              <div><img :src="video.cover" class="cover"/> </div>
              <div class="details">
                <h2 class="video-title">
                  {{ video.title }}
                </h2>
                <p class="subtitle">{{ video.subtitle }}</p>
              </div>
            </div>
            <div class="actions">
              <button @click="removeVideo(video)" class="delete">
                <img src="../static/img/images.png" alt="times">
              </button>
            </div>
          </li>
        </ul>
      </section>
</template>

<script>
export default {
  name: "PlayList",
  props: ['videos'],
  data: () => ({
  }),
  methods: {
    chooseVideo(video) {
      this.$emit('choose', video);

    },
    removeVideo(video) {
      this.$emit('remove', video);
    }
  }
}
</script>

<style scoped>
.playlist {
  max-width: 375px;
  max-height: 623px;
  margin: 0 auto;
  margin: 0;
  box-sizing: border-box;
  background-color: #fff;
  overflow-y: auto;
  border-radius: 5px;
}

.playlist h3 {
  color: #212121;
  font-size: 18px;
  font-weight: 400;
  margin-top: 20px;
  margin-bottom: 20px;
  text-align: center;
}
.playlist .video-list {
  padding: 10px;
}
.cover-playlist {
  display: flex;
}

.playlist .video-list {
  display: flex;
  padding: 10px;
}

.playlist .video-list:hover {
  background-color: #ededed;
  transition: box-shadow .2s,background-color .3s;
  cursor: pointer;
}
.cover {
  width: 50px;
  height: 100%;
  box-shadow: 0 24px 35px -16px rgb(107 179 237);
  border-radius: 5px;
}


.details {
  margin-left: 10px;
  width: 200px;
}
.details > .video-title {
  color: #585858;
  font-size: inherit;
  text-align: left;
}

.details > .subtitle {
  color: #5d5555;
  text-align: left;
}

.video-title {
  margin-bottom: 5px;
}
.actions > .delete {
  border-radius: 50%;
  width: 40px;
  height: 40px;
  justify-content: center;
  box-shadow: -1px 17px 24px -6px rgba(0,0,0,.2);
  cursor: pointer;
  font-size: 20px;
  color: #ba83ca;
}
button img {
  width: 12px;
}
button:hover {
  opacity: 0.8;
  transform: scale(1.1);
}
::-webkit-scrollbar-track
{
  -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
  background-color: #F5F5F5;
}

::-webkit-scrollbar
{
  width: 10px;
  background-color: #F5F5F5;
}

::-webkit-scrollbar-thumb
{
  background-color: #ba83ca;
  background-image: -webkit-linear-gradient(45deg,
  rgba(255, 255, 255, .2) 25%,
  transparent 25%,
  transparent 50%,
  rgba(255, 255, 255, .2) 50%,
  rgba(255, 255, 255, .2) 75%,
  transparent 75%,
  transparent)
}

</style>
