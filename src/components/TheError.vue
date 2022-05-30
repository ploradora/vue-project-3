<template>
  <section>
    <p>Make sure you select a rating</p>
    <div class="close" @click="closeError">x</div>
  </section>
  <div class="overlay" @click="closeError"></div>
</template>

<script>
export default {
  emits: ["show-error"],
  data() {
    return {
      errorClose: false,
    };
  },
  methods: {
    closeError() {
      this.$emit("show-error", this.errorClose);
    },
  },
};
</script>

<style scoped lang="scss">
section {
  position: absolute;
  background-color: hsl(212, 12%, 25%);
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  padding: 2rem;
  border-radius: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  p {
    text-align: center;
    color: #fff;
  }
  .close {
    position: relative;
    cursor: pointer;
    font-weight: 700;
    color: #fff;
    margin-top: 1.4rem;
    &::after {
      background-color: hsl(213, 5%, 43%);
      position: absolute;
      content: "";
      width: 2rem;
      height: 2rem;
      border-radius: 50%;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      z-index: -1;
    }
    &:hover {
      &:after {
        background-color: hsl(210, 3%, 53%);
      }
    }
  }
}
.overlay {
  position: absolute;
  content: "";
  background-color: rgba(51, 51, 51, 0.452);
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  backdrop-filter: blur(4px);
  cursor: pointer;
}
</style>
