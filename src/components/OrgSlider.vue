<template>
  <section class="orgSlider flex items-center rounded-lg p-5">
    <div class="slider flex items-center justify-center cursor-pointer shadow-lg">
      <button>
        <img
          class="slider--left"
          src="../assets/arrow-left.svg"
          alt="slider-img"
        />
      </button>
    </div>
    <div class="card">
      <img 
        class="card__img"
        src="" 
        alt="" 
        />
    </div>
    <div class="slider flex items-center justify-center cursor-pointer shadow-lg">
      <button>
        <img
          class="slider--right"
          src="../assets/arrow-right.svg"
          alt="slider"
        />
      </button>
    </div>
  </section>
</template>
<script>
export default {};
</script>
<style lang="scss">
$primary-background: #F9FAFB;
// $primary-background: #af24ffda;
$secondary-background: #ffffff;
.orgSlider {
  width: 50.125rem;
  height: 8rem;
  background: $primary-background;
  .slider {
    width: 4.6875rem;
    height: 4.6875rem;
    background: $secondary-background;
    border-radius: 0.625rem;
    // &--left,
    // &--right {
    //   width: 4.6875rem;
    //   height: 4.6875rem;
    // }
  }
}
</style>
