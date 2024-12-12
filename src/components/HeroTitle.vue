<script setup>
</script>

<template>
  <div id="title-wrapper">
    <p class="title-font-size title-font-weight" id="we-are">WE'RE</p>
    <p class="title-font-size title-font-weight title-font-spacing">COMING</p>
    <p class="title-font-size title-font-weight title-font-spacing">SOON</p>
  </div>
</template>

<style scoped>
#title-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  font-family: 'Josefin Sans', sans-serif;
}

.title-font-size {
  font-size: 56px;
}

.title-font-weight {
  font-weight: 400;
}

.title-font-spacing {
  letter-spacing: 0.5rem;
}

#we-are {
  font-weight: 100;
  letter-spacing: 0.5rem;
  color: var(--primary-desaturated-red)
}

@media (min-width: 1024px) {
  #title-wrapper {
    display: flex;
    flex-direction: column;
    width: 100%;
    font-family: 'Josefin Sans', sans-serif;
  }

  .title-font-size {
    font-size: 72px;
  }

  .title-font-spacing {
    letter-spacing: 1rem;
  }

  #we-are {
    letter-spacing: 1rem;
  }
}
</style>
