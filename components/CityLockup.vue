<template>
  <div class="city">
    <div class="city-icon" />
    <nuxt-link to="/location" class="city-title">
          Providence
    </nuxt-link>
  </div>
</template>

<style>
.city-title {
  font-size: 2.25rem;
  color: var(--offBlack);
  text-decoration: none;
  &:hover {
    color: var(--gold);
  }
}
</style>


