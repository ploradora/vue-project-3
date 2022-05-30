<template>
  <teleport to="body">
    <div class="attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
        >Frontend Mentor</a
      >. Coded by <a href="#">Plora Dora</a>.
    </div>
  </teleport>
</template>

<style scoped lang="scss">
.attribution {
  position: absolute;
  left: 50%;
  bottom: 1rem;
  transform: translateX(-50%);
  font-size: 11px;
  text-align: center;
  color: #fff;
  width: 100%;
  a {
    color: hsl(0, 0%, 69%);
  }
}
</style>
