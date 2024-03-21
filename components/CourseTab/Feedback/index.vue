<template>
  <div>
    <h3>Rate This Course</h3>
    <div class="rating">
      <input type="radio" id="star5" name="rating" value="5" v-model="rating" />
      <label for="star5" title="5 stars">
        <Icon name="gravity-ui:star-fill" />
      </label>
      <input type="radio" id="star4" name="rating" value="4" v-model="rating" />
      <label for="star4" title="4 stars">
        <Icon name="gravity-ui:star-fill"
      /></label>
      <input type="radio" id="star3" name="rating" value="3" v-model="rating" />
      <label for="star3" title="3 stars">
        <Icon name="gravity-ui:star-fill"
      /></label>
      <input type="radio" id="star2" name="rating" value="2" v-model="rating" />
      <label for="star2" title="2 stars">
        <Icon name="gravity-ui:star-fill"
      /></label>
      <input type="radio" id="star1" name="rating" value="1" v-model="rating" />
      <label for="star1" title="1 star">
        <Icon name="gravity-ui:star-fill"
      /></label>
    </div>
    <div>
      <Textarea v-model="comment" placeholder="Write your comment here" />
    </div>
    <Button @click="submitRating" class="mt-4">Submit</Button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      rating: null,
      comment: "",
    };
  },
  methods: {
    submitRating() {
      if (!this.rating) {
        alert("Please select a rating");
        return;
      }
      // Here you can handle the submission of rating and comment, e.g., send it to a server
      console.log("Rating:", this.rating);
      console.log("Comment:", this.comment);
      // Reset fields after submission
      this.rating = null;
      this.comment = "";
    },
  },
};
</script>

<style scoped>
.rating {
  display: flex;
}

.rating input {
  display: none;
}

.rating label {
  cursor: pointer;
  width: 25px;
  font-size: 20px;
  color: #ddd;
}

.rating input:checked ~ label {
  color: #f90;
}
</style>
