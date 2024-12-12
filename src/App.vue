<script setup>
import LogoComponent from '@/components/LogoComponent.vue'
import HeroTitle from './components/HeroTitle.vue'
import HeroDescription from './components/HeroDescription.vue'
import EmailAddressInput from './components/EmailAddressInput.vue'
import { toast } from 'vue3-toastify'

const handleEmailSubmit = (emailValue) => {
  console.log('emailValue:', emailValue)
  toast(`Successful email sent to: ${emailValue}`)
}
</script>

<template>
  <div class="section-gradient-light" id="mobile-wrapper">
    <div id="mobile-logo">
      <LogoComponent />
    </div>
    <img
      alt="Vue logo"
      class="mobile-hero-image"
      src="../public/hero-mobile.jpg"
      width="375"
      height="250"
    />
    <div id="mobile-content-wrapper">
      <HeroTitle />
      <HeroDescription />
      <EmailAddressInput @submit="handleEmailSubmit" />
    </div>
  </div>
  <div class="section-gradient-light" id="desktop-wrapper">
    <div id="desktop-content-wrapper">
      <LogoComponent />
      <div id="desktop-message">
        <HeroTitle />
        <HeroDescription />
        <EmailAddressInput @submit="handleEmailSubmit"/>
      </div>
    </div>
    <img
      alt="Vue logo"
      class="desktop-hero-image"
      src="../public/hero-desktop.jpg"
      width="610"
      height="800"
    />
  </div>
</template>

<style scoped>
#mobile-wrapper {
  display: flex;
  flex-direction: column;
  overflow: auto;
  height: 100vh;
  width: 100vw;
}

#mobile-logo {
  padding: 2rem;
}

#mobile-content-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  padding: 4rem 2rem;
  gap: 1rem;
}

#desktop-wrapper {
  display: none;
}

.mobile-hero-image {
  width: 100%;
  height: auto;
  object-fit: cover;
  object-position: center;
}

/* For desktops (screens larger than 1024px) */
@media (min-width: 1024px) {
  #mobile-wrapper {
    display: none;
  }

  #desktop-wrapper {
    display: grid;
    grid-template-columns: 2fr 1fr;
    height: 100vh;
    width: 100vw;
  }

  #desktop-content-wrapper {
    display: grid;
    grid-template-rows: 0.1fr 1fr;
    width: 50%;
    align-items: center;
    justify-items: start;
    margin: 4rem auto 4rem auto;
  }

  #desktop-message {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .desktop-hero-image {
    display: flex;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    visibility: visible;
  }
}

@media (min-width: 1500px) {
  #mobile-wrapper {
    display: none;
  }

  #desktop-wrapper {
    display: grid;
    grid-template-columns: 2fr 1.5fr;
    height: 100vh;
    width: 100vw;
  }

  #desktop-message {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  #desktop-content-wrapper {
    display: grid;
    grid-template-rows: 0.1fr 1fr;
    width: 60%;
    align-items: center;
    justify-items: start;
    margin: 4rem auto 4rem auto;
  }
}
</style>
