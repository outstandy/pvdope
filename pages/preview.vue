<template>
  <section class="container">
    <transition appear name="img-transition">
      <div id="img" class="img" />
    </transition>
    <transition-group appear name="card-transition" tag="div">
      <div key="1" id="card" class="city-card">
        <div class="city-card__icon" />
        <label class="city-card__nickname">The Barbary Coast</label>
        <h1 class="city-card__title"> San Francisco </h1>
        <hr />
        <p class="city-card__description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Enim voluptas beatae aut rerum, placeat similique ut sapiente repellat sit tenetur itaque excepturi dolore nisi! Amet cumque molestias iure eius nihil.</p>
        <nuxt-link class="button" to="/location">Visit</nuxt-link>
      </div>
    </transition-group>
  </section>
</template>
<script>
  export default {
    beforeRouteLeave (to, from, next) {
      const card = document.getElementById("card")
      const img = document.getElementById("img")
      card.classList.add("card-transition-leave-active", "card-transition-leave-to");
      img.classList.add("img-transition-leave-active", "img-transition-leave-to");
      next()
    }
  }
</script>

<style scoped lang='sass'>
@import url('~/static/styles/variables.css')

.container
  display: flex;
  height: 100vh
  width: 100vw
  position: absolute
  align-items: center
  justify-content: center

.img
  background-image: url('~/assets/img/sf.jpeg')
  background-size: cover
  height: calc(100% - (1.5 * var(--spaceXXLarge)))
  width: calc(100% - (1.5 * var(--spaceXXLarge)))
  background-color: var(--offWhite)
  box-shadow: 0 10px 20px 0 rgba(109,101,103,0.25)
  border-radius: 3px

.city-card
  background-color: var(--offWhite)
  box-shadow: 0 10px 20px 0 rgba(109,101,103,0.25)
  border-radius: 3px
  position: absolute
  padding: var(--spaceLarge)
  max-width: 550px
  left: var(--spaceMed)
  text-align: center
  top: 50%
  transform: translate(0%,-50%);

  &__icon
    height: 50px
    width: 50px
    border-radius: 100%
    display: inline-block
    border: 1px solid var(--gray)
    margin-bottom: var(--space)

  &__title
    margin-bottom: var(--space)

  hr
    margin-bottom: var(--spaceMed)

  &__description
    margin-bottom: var(--spaceMed)

  &__nickname
    display: block

.card-transition-enter-active,
.card-transition-leave-active
  transition: all 1s ease
  .city-card__nickname
    transition: all 0.8s ease
    transition-delay: 0.1s
  .city-card__title
    transition: all 0.8s ease
    transition-delay: 0.15s
  hr
    transition: all 0.8s ease
    transition-delay: 0.2s
  .city-card__description
    transition: all 0.8s ease
    transition-delay: 0.2s
  .button
    transition: all 0.8s ease
    transition-delay: 0.4s

.card-transition-leave-active
  transition: all 0.5s ease
  .city-card__title,
  .city-card__nickname,
  .city-card__description,
  .button
    transition: all 0.5s ease


.card-transition-enter,
.card-transition-leave-to
  transform: translateY(10px)
  .city-card__icon,
  .city-card__nickname,
  .city-card__title,
  .city-card__description,
  .button
    opacity: 0
    transform: translateY(25px)
  hr
    transform: scaleX(0)

.img-transition-enter-active,
.img-transition-leave-active
  transition: all 0.6s ease-in-out

.img-transition-enter,
.img-transition-leave-to
  transform: translateY(5px)
  
  
</style>