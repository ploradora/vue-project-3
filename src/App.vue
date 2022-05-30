<template>
  <rating-card
    v-if="hideRatingCard"
    @submiting-rating="ratingSubmited"
  ></rating-card>
  <submited-card v-if="validRating" :rating="this.passedRating"></submited-card>
  <the-attribution></the-attribution>
</template>

<script>
import RatingCard from "./components/RatingCard.vue";
import TheAttribution from "./components/TheAttribution.vue";
import SubmitedCard from "./components/SubmitedCard.vue";

export default {
  components: {
    RatingCard,
    TheAttribution,
    SubmitedCard,
  },
  data() {
    return {
      passedRating: null,
      validRating: false,
      hideRatingCard: true,
    };
  },
  methods: {
    ratingSubmited(rating) {
      this.passedRating = rating;
      this.validRating = true;
      this.hideRatingCard = false;
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Overpass:wght@400;700&display=swap");

.card-container {
  margin: auto;
  width: 90%;
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 410px;
  padding: 1.3rem;
  border-radius: 20px;
  background-color: hsl(210, 19%, 15%);
}
</style>
