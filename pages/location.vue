<template>
  <section class="container">
    <transition appear name="img-transition">
      <div id="img" class="img" />
    </transition>
    <transition-group appear name="block-transition" tag="div">
      <div key="0" class="block-container">
        <div key="1" class="block block--hed">
          <div key="2" class="block__siderail">
            <div key="3" class="block__icon" />
          </div>
          <div key="4" class="block__main">
            <h1 key="5" class="block__title">San Francisco</h1>
          </div>
        </div>
        <div key="6" class="block block--subhed">
          <div key="7" class="block__siderail">
            <label key="8" class="block__label">The Barbary Coast</label>
          </div>
          <div key="9" class="block__main">
            <p key="10">So when is it okay to use lorem ipsum? First, lorem ipsum works well for staging. It's like the props in a furniture store—<nuxt-link to="/">filler text</nuxt-link> makes it look like someone is home. The same Wordpress template might eventually be home to a fitness blog, a photography website, or the online journal of a cupcake fanatic. Lorem ipsum helps them imagine what the lived-in website might look like.</p>
          </div>
        </div>
        <div key="11" class="block block--stats">
          <div key="12" class="block__siderail">
            <label key="13" class="block__label">Statistics</label>
          </div>
          <div key="14" class="block__main block__main--stats">
            <div key="15" class="stat">
              <h3 key="19">10,000</h3>
              <p key="20" class="footnote">Quantified thing</p>
            </div>
            <div key="16" class="stat">
              <h3 key="21">10,000</h3>
              <p key="22" class="footnote">Quantified thing</p>
            </div>
            <div key="17" class="stat">
              <h3 key="23">10,000</h3>
              <p key="24" class="footnote">Quantified thing</p>
            </div>
            <div key="18" class="stat">
              <h3 key="25">10,000</h3>
              <p key="26" class="footnote">Quantified thing</p>
            </div>
          </div>
        </div>
        <div key="27" class="block block--stuff">
          <div key="28" class="block__siderail">
            <label key="29" class="block__label">What to do</label>
          </div>
          <div key="4" class="block__main">
            <h4>Magnolia Brew Pub</h4>
          </div>
        </div>
      </div>
    </transition-group>
  </section>
</template>
<script>
//   export default {
//     beforeRouteLeave (to, from, next) {
//       const card = document.getElementById("card")
//       const img = document.getElementById("img")
//       card.classList.add("card-transition-leave-active", "card-transition-leave-to");
//       img.classList.add("img-transition-leave-active", "img-transition-leave-to");
//       next()
//     }
//   }
</script>

<style scoped lang='sass'>
@import url('~/static/styles/variables.css')

.container
    position: relative

.img
  background-image: url('~/assets/img/sf.jpeg')
  background-size: cover
  height: 100vh
  width: 100vw
  padding: var(--spaceMed)
  position: absolute
  z-index: -1

.block-container
  background-color: var(--offWhite)
  box-shadow: 0 10px 20px 0 rgba(109,101,103,0.25)
  height: 100vh
  max-width: 700px
  width: 75vw
  z-index: 1
  padding: var(--spaceXLarge)
  overflow-y: scroll

.block
  display: flex
  flex-direction: row
  margin-bottom: var(--spaceXLarge)

  &--hed
    top: 0
    align-self: flex-start
    align-items: center
    margin-bottom: var(--space)
    position: sticky

  &--subhed

  &__siderail
    width: 50px
    margin-right: var(--spaceLarge)

  &__main
    &--stats
      display: flex
      flex-direction: row
      flex-wrap: wrap
      width: 100%

      .stat
        width: 50%
        padding-right: var(--spaceSmall)
        margin-bottom: var(--spaceMed)

  &__icon
    height: 50px
    width: 50px
    border-radius: 50px
    border: 1px solid var(--gray)
    margin-bottom: var(--space)
    margin: 0 auto

  &__label
    display: block
    white-space: nowrap
    transform: rotate(90deg) translateY(-25px)
    transform-origin: left


.img-transition-enter-active,
.img-transition-leave-active
  transition: all 0.6s ease-in-out

.img-transition-enter,
.img-transition-leave-to
  transform: translateX(-10px)

.block-transition-enter-active,
.block-transition-leave-active
  transition: all 0.8s ease-in-out
  .block__icon
    transition: all 0.6s ease-in-out
    transition-delay: 0.1s
  .block__title,
  .block__label,
  h3
    transition: all 0.6s ease-in-out
    transition-delay: 0.2s    
  .footnote
    transition: all 0.6s ease-in-out
    transition-delay: 0.4s
  p
    transition: all 0.6s ease-in-out
    transition-delay: 0.2s
  

.block-transition-enter,
.block-transition-leave-to
  *
    opacity: 0
  .block-container
    transform: translateX(-25px)
  .block__icon
    transform: scale(0.75)
  .block__title,
  h3
    transform: translateX(-10px)
  .block__label
    transform: rotate(90deg) translateY(-25px) translateX(-20px)
  p
    transform: translateX(-10px)

</style>