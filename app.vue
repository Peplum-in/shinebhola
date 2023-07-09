<template>
  <div class="section py-5">
    <div class="columns is-hidden-touch pt-0">
      <div class="column is-2">
        <nuxt-link to="/" class="has-text-dark is-size-5">
          Company Name
        </nuxt-link>
        <p>Brings life to still shots</p>
        <br>
        <div>

          <ul>
            <li>

              <nuxt-link v-for="(nav, index) in navigation" :key="index" to="/"
                class="is-block has-text-dark has-text-weight-semibold pr-3">

                {{ nav.name }}
              </nuxt-link>

            </li>
          </ul>
        </div>
        <div class="mb-5 mt-3">

          <ul>
            <li>

              <nuxt-link v-for="(nav, index) in sub_navigation" :key="index" to="/" class="is-block  pr-3 has-text-dark">

                {{ nav.name }}
              </nuxt-link>

            </li>
          </ul>
        </div>
        <div class="my-5">

          <ul>
            <li>

              <nuxt-link v-for="(nav, index) in follows" :key="index" to="/" class="is-block  pr-3 has-text-dark">

                {{ nav.name }}
              </nuxt-link>

            </li>
          </ul>
        </div>
      </div>
      <div class="column ">
        <NuxtPage />

      </div>
    </div>
    <div class="is-hidden-desktop">
      <div class="level is-mobile">
        <div class="level-left">
          <div class="level-item">
            <div>
              Company Name
            </div>
          </div>
        </div>
        <div class="level-right">
          <div class="level-item">
            <div>
              <p @click="showNav" v-if="!showMobileNav" class="is-clickable has-text-weight-semibold has-text-dark">Menu
              </p>
              <p @click="showNav" v-if="showMobileNav" class="is-clickable shas-text-weight-semibold has-text-dark">Close
              </p>

            </div>
          </div>
        </div>
      </div>
      <div class="mobile-nav" v-show="showMobileNav">
        <ul>
          <nuxt-link v-for="(nav, index) in navigation" :key="index" to="/"
            class="level-item has-text-weight-semibold pr-3">

            {{ nav.name }}
          </nuxt-link>

        </ul>
      </div>
    </div>

  </div>
</template>

<script setup>
const showMobileNav = ref(false)

function showNav() {
  showMobileNav.value = !showMobileNav.value
}

const route = useRoute();

watch(route, value => {
  showMobileNav.value = false
}, { deep: true, immediate: true })

const navigation = [
  {
    'name': 'Home',
    'to': '/',
  },
  {
    'name': 'Architecture',
    'to': '/',
  },
  {
    'name': 'Bespoke',
    'to': '/',
  },
  {
    'name': 'Product',
    'to': '/',
  },
  {
    'name': 'Portraits',
    'to': '/',
  },
  {
    'name': 'Travel',
    'to': '/',
  },
  {
    'name': 'Contact',
    'to': '/',
  },
];
const sub_navigation = [
  {
    'name': 'About',
    'to': '/',
  },
  {
    'name': 'Clients',
    'to': '/',
  },
  {
    'name': 'Services',
    'to': '/',
  },
];
const follows = [
  {
    'name': 'Facebook',
    'to': '/',
  },
  {
    'name': 'Instagram',
    'to': '/',
  },
  {
    'name': 'Whatsapp',
    'to': '/',
  },
  {
    'name': 'Email',
    'to': '/',
  },
];

</script>
<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";
@import url('https://fonts.googleapis.com/css2?family=DM Sans:wght@400;600&display=swap');

* {
  font-family: 'DM Sans', sans-serif;
}

/* html {
  background-color: #ffd202;
  scroll-behavior: smooth;
} */

body {
  max-width: 100vw;
  /* min-height: calc(100vh - var(--wp-admin--admin-bar--height, 0px)); */
  background-color: #fefefe;
  /* grid-template-rows: auto 1fr; */
  margin: 0;
  /* display: grid; */
  overflow-x: hidden;
  overflow-y: auto;
}

.page-enter-active,
.page-leave-active {
  transition: all 0.4s;
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: blur(1rem);
}
</style>