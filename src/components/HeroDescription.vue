<script setup>
</script>

<template>
  <div id="desc-wrapper">
    <p>Hello fellow shoppers! We're currently building our new fashion store. Add your email below to stay up-to-date with announcements and our launch deals.</p>
  </div>
</template>

<style scoped>
#desc-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 100%;
  font-family: 'Josefin Sans', sans-serif;
}

p {
  color: var(--primary-desaturated-red);
  line-height: 1.5rem;
}

@media (min-width: 1024px) {
  #desc-wrapper {
    display: flex;
    flex-direction: column;
  }
}
</style>
