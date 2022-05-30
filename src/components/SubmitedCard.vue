<template>
  <section>
    <img
      class="illustration"
      src="../assets/images/illustration-thank-you.svg"
      alt="POS illustration"
    />
    <p class="rating-selected">You selected {{rating}} out of 5</p>
    <h1>Thank you!</h1>
    <p>
      We appreciate you taking the time to give a rating. If you ever need more
      support, don’t hesitate to get in touch!
    </p>
  </section>
</template>

<script>
export default {
  props: ['rating'],
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
  .illustration {
    display: block;
  }
  .rating-selected {
    margin-top: 1.2rem;
    border-radius: 30px;
    padding: 0.4rem 1.4rem;
    background-color: hsl(213, 19%, 18%);
    color: hsl(25, 97%, 53%);
  }
  h1 {
    color: #fff;
    margin-top: 1.5rem;
    margin-bottom: 1rem;
  }
  p {
    text-align: center;
    color: hsl(217, 12%, 63%);
  }
}
</style>
