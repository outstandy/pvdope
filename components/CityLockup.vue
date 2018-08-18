<template>
  <transition-group appear name="lockup-transition">
    <div key="1" class="city">
      <div key="2" class="city-icon" />
      <h1 key="3" class="city-title">{{ city }}</h1>
      <label key="4" class='city-nickname'> {{ nickname }} </label>
    </div>
  </transition-group>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'CityLockup',
  props: [
    'city',
    'nickname'
  ],
  computed: mapState(['page']),
}
</script>

<style scoped lang="sass">
@import url('~/static/styles/variables.css')

.city 
  align-items: center
  display: flex
  flex-direction: column
  transition: all 0.25s ease

  &:hover
    .city-icon
      border-color: var(--gold)
    .city-title,
    .city-nickname
      color: var(--gold)

.city-icon 
  border: 1px solid
  border-color: var(--offBlack)
  border-radius: 100%
  height: 100px
  margin-bottom: var(--space)
  width: 100px
  transition: all 0.25s ease

.city-title 
  font-size: 2.25rem
  transition: all 0.25s ease
  margin-bottom: var(--spaceSmall)

.lockup-transition-enter-active,
.lockup-transition-leave-active
  transition: all 1s ease
  .city-icon
    transition: all 0.8s ease
  .city-title
    transition: all 0.8s ease
    transition-delay: 0.1s
  .city-nickname
    transition: all 0.8s ease
    transition-delay: 0.2s

.lockup-transition-leave-active
  transition: all 0.3s ease
  .city-icon
    transition-delay: 0.2s
  .city-title
    transition-delay: 0.1s
  .city-nickname
    transition-delay: 0s


.lockup-transition-enter
  transform: translateY(10px)
  .city-icon
    opacity: 0
    transform: scale(0.5)
  .city-title,
  .city-nickname
    opacity: 0
    transform: translateY(10px)

.lockup-transition-leave-to
  .city-icon,
  .city-title,
  .city-nickname
    opacity: 0
    transform: translateY(10px)


</style>


