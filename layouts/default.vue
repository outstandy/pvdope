<template>
  <div>
    <nuxt/>
  </div>
</template>

<script>

</script>

<style lang="sass">
@import url('~/static/styles/fonts.css')
@import url('~/static/styles/variables.css')
@import url('~/static/styles/typography.css')
@import url('~/assets/main.css')

html 
  background-color: var(--offWhite)
  font-size: 14px
  -ms-text-size-adjust: 100%
  -webkit-text-size-adjust: 100%
  -moz-osx-font-smoothing: grayscale
  -webkit-font-smoothing: antialiased
  box-sizing: border-box


*, *:before, *:after 
  box-sizing: border-box
  margin: 0

hr
  border: 0
  height: 0
  border-bottom: 1px solid rgba(129, 131, 133, 0.25)

.button
  background-color: var(--gold)
  border-radius: 2px
  box-shadow: 0 2px 5px rgba(129, 131, 133, 0.25)
  color: var(--offWhite)
  display: inline-block
  letter-spacing: 2px
  cursor: pointer
  text-transform: uppercase
  padding: var(--spaceSmall) var(--space)
  text-align: center
  transition: all 0.3s ease

  &:hover
    box-shadow: 0 3px 6px rgba(129, 131, 133, 0.4)
    color: var(--offWhite)
    transform: translateY(-1px)

.city-container 
  align-items: center
  display: flex
  justify-content: space-around
  height: 100vh
  position: absolute
  width: 100vw

</style>

