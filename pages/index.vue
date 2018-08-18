<template>
    <div class="city-container">
      <nuxt-link class="city-link" to="/preview">
        <city-lockup city="San Francisco" nickname="The Barbary Coast" />
      </nuxt-link>
      <p>Choose a city.</p>
      <nuxt-link class="city-link" to="/preview">
        <city-lockup city="Providence" nickname="The Renaissance City" />
      </nuxt-link>
    </div>
</template>

<script>
import CityLockup from '~/components/CityLockup.vue'

export default {
  beforeRouteLeave (to, from, next) {
    const cities = document.getElementsByClassName("city")
    Array.from(cities).forEach(city => city.classList.add("lockup-transition-leave-active", "lockup-transition-leave-to"));
    next()
  },
  components: {
    CityLockup
  }
}
</script>

<style scoped lang="sass">
.city-container 
  height: 100vh
  position: absolute
  width: 100vw
  display: flex
  align-items: center
  justify-content: space-evenly
  text-align: center

.city-link
  text-decoration: none

</style>

