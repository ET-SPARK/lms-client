      <!--  a simple card to test a vidiomodal is correctly worked just a test purpose  -->


<template>
  <div>
    <div class="p-4">
      <div
        v-for="(video, index) in videos"
        :key="index"
        @click="openModal(video)"
        class="cursor-pointer"
      >
        <h3 class="text-xl font-bold mb-2">upcoming course3</h3>
      </div>
    </div>
    <vidiomodal
      v-if="selectedVideo"
      :videoUrl="selectedVideo.url"
      :videoTitle="selectedVideo.title"
      :videoDescription="selectedVideo.description"
      @close="closeModal"
    />
  </div>
</template>

<script>
import vidiomodal from "~/components/vidiomodal.vue";

export default {
  components: {
    vidiomodal,
  },
  data() {
    return {
      videos: [
        {
          title: "Video 1",
          description: "Description of Video 1",
          url: "path_to_video_1.mp4",
        },

        // Add more videos as needed
      ],
      selectedVideo: null,
    };
  },
  methods: {
    openModal(video) {
      this.selectedVideo = video;
    },
    closeModal() {
      this.selectedVideo = null;
    },
  },
};
</script>
