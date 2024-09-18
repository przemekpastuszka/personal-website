<template>
  <section class="experience">
    <div class="container">
      <slot/>
    </div>
  </section>
</template>

<style scoped>
.experience {
  padding: 10px 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>