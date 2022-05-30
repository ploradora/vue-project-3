<template>
  <section>
    <div class="star-background">
      <img src="../assets/images/icon-star.svg" alt="icon star" class="star" />
    </div>
    <h1>How did we do?</h1>
    <p>
      Please let us know how we did with your support request. All feedback is
      appreciated to help us improve our offering!
    </p>
    <div class="ratings">
      <button
        v-for="rating in ratings"
        :key="rating"
        :class="{ active: selectedRating === rating }"
        @click="selectRating(rating)"
      >
        {{ rating }}
      </button>
    </div>
    <button class="submit" @click="submitRating">Submit</button>
  </section>
  <the-error v-if="error" @show-error="closeError"></the-error>
</template>

<script>
import TheError from "../components/TheError.vue";
export default {
  emits: ["submiting-rating"],
  components: {
    TheError,
  },
  data() {
    return {
      ratings: [1, 2, 3, 4, 5],
      selectedRating: null,
      error: false,
    };
  },
  methods: {
    selectRating(rating) {
      this.selectedRating = rating;
    },
    submitRating() {
      if (this.selectedRating === null) {
        this.error = true;
        return;
      }
      this.$emit("submiting-rating", this.selectedRating);
    },
    closeError(err) {
        this.error = err
    }
  },
};
</script>

<style scoped lang="scss">
section {
  margin: auto;
  width: 90%;
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 410px;
  padding: 1.3rem;
  border-radius: 20px;
  background-color: hsl(210, 19%, 15%);
  .star-background {
    width: fit-content;
    padding: 0.8rem;
    align-self: flex-start;
    border-radius: 50%;
    background-color: hsl(213, 19%, 18%);
    margin-bottom: 1rem;
    cursor: pointer;
    &:hover {
      background-color: hsl(215, 7%, 35%);
    }
    .star {
      display: block;
      position: relative;
      width: 0.8rem;
    }
  }
  h1 {
    font-size: 1.75rem;
    color: #fff;
    margin-top: 1rem;
    margin-bottom: 0.8rem;
    align-self: flex-start;
  }
  p {
    color: hsl(217, 12%, 63%);
  }
  .ratings {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 1.5rem 0;
    width: 100%;
    button {
      border: none;
      font-size: 0.8rem;
      font-family: "Overpass", sans-serif;
      color: hsl(216, 12%, 54%);
      background-color: hsl(213, 19%, 18%);
      width: 2.7rem;
      height: 2.7rem;
      border-radius: 50%;
      cursor: pointer;
      &:hover {
        color: #fff;
        background-color: hsl(216, 12%, 54%);
      }
    }
    .active {
      background-color: hsl(25, 97%, 53%);
      color: #fff;
      &:hover {
        background-color: hsl(25, 97%, 53%);
      }
    }
  }
  .submit {
    width: 100%;
    background-color: hsl(25, 97%, 53%);
    border-radius: 100px;
    font-size: 0.8rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.2rem;
    color: #fff;
    border: none;
    padding: 0.8rem 0;
    cursor: pointer;
    &:hover {
      color: hsl(25, 97%, 53%);
      background-color: #fff;
    }
  }
}
</style>
