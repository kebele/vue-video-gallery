<template>
  <div>
    <h3 class="heading">video gallery</h3>
    <div class="container">
      <div class="main-video">
        <div class="video">
          <video :src="mainVideoSrc" controls autoplay></video>
          <h3 class="title">{{ videoTitle }}</h3>
        </div>
      </div>

      <div class="video-list">
        <div
          class="vid"
          v-for="(video, index) in videos"
          :key="index"
          @click="videoGallery(videos[index])"
        >
          <video :src="video.src"></video>
          <h3 class="title">{{ index + 1 }} - {{ video.title }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { videos } from "../utils/videos";
export default {
  data() {
    return {
      videos,
      mainVideoSrc: videos[0].src,
      videoTitle: videos[0].title,
    };
  },
  methods: {
    videoGallery(id) {
      console.log("clicked", id);
      this.mainVideoSrc = id.src;
      this.videoTitle = id.title;
    },
  },
};
</script>

<style scoped></style>
