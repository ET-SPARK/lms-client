      <!--  a vidio component for a course  a component used for a page that render a vidio -->

  <template>
    <div class="video-section">
      <button @click="showVideo = true" class="bg-blue-500 text-white font-bold py-2 px-4 rounded">
        Show Video
      </button>
  
      <div v-if="showVideo" class="w-3/4 mx-auto mt-4">
        <video class="w-full" style="height: 500px;" controls>
          <source src="../static/country-info.mp4" type="video/mp4" />
          Your browser does not support the video tag.
        </video>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showVideo: false,
      };
    },
    props: {
      videoUrl: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style>
  /* Add your component-specific styles here */
  </style>
  