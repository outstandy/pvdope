<template>
    <nuxt-link to="/location" class="city">
      <div class="city-icon" />
      <h1 class="city-title">{{ city }}</h1>
      <label class='city-nickname'> City Nickname Here </label>
    </nuxt-link>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data() {
    return {
      isActive: false
    }
  },
  name: 'CityLockup',
  props: [
    'city',
  ],
  computed: mapState(['page']),
}
</script>

<style>

.city {
  align-items: center;
  display: flex;
  flex-direction: column;
  text-decoration: none;
  transition: all 0.25s ease-in-out;
}

.city-icon {
  border: 1px solid; 
  border-color: var(--offBlack);
  border-radius: 100%;
  height: 100px;
  margin-bottom: var(--spaceMed);
  width: 100px;
  transition: all 0.25s ease-in-out;
}

.city-title {
  font-size: 2.25rem;
  color: var(--offBlack);
  transition: all 0.25s ease;
}

</style>


