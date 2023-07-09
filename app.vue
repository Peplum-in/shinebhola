<template>
  <div class="section py-0 ">
    <div class="columns py-6 is-hidden-touch pt-0">
      <div class="column is-2">
        <nuxt-link to="/" class="has-text-dark is-size-5">
          Company Name
        </nuxt-link>
        <p>Brings life to still shots</p>
        <br>
        <div>

          <ul>
            <li>

              <nuxt-link v-for="(nav, index) in navigation" :key="index" :to="nav.to"
                class="is-block has-text-dark has-text-weight-semibold pr-3">

                {{ nav.name }}
              </nuxt-link>

            </li>
          </ul>
        </div>
        <div class="mb-5 mt-3">

          <ul>
            <li>

              <nuxt-link v-for="(nav, index) in sub_navigation" :key="index" :to="nav.to"
                class="is-block  pr-3 has-text-dark">

                {{ nav.name }}
              </nuxt-link>

            </li>
          </ul>
        </div>
        <div class="my-5">

          <ul>
            <li>

              <nuxt-link v-for="(nav, index) in follows" :key="index" :to="nav.to" class="is-block  pr-3 has-text-dark">

                {{ nav.name }}
              </nuxt-link>

            </li>
          </ul>
        </div>
        <div class="my-5">

          <ul>
            <li>

              <a v-for="(nav, index) in abs_contact" :key="index" :href="nav.link"
                class="is-block heading has-text-weight-semibold  pr-3 has-text-dark">

                {{ nav.name }} ↗
              </a>

            </li>
          </ul>
        </div>
      </div>
      <div class="column ">
        <div class="columns">
          <div class="column is-8-desktop">

            <p class="title is-size-5">
    
              Product Photography
            </p>
            <p class="subtitle is-sisze-7">
    
              
              
              The products are the static entities that I see and work with every day. To be significant, products are objects
              that we want to touch and feel rather seeing them in images. For this reason, I always add a story behind every
              product I work with.
              
            </p>
          </div>
        </div>
        <br>
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
          <nuxt-link v-for="(nav, index) in navigation" :key="index" :to="nav.to"
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

];
const sub_navigation = [
  {
    'name': 'About',
    'to': '/about',
  },
  {
    'name': 'Clients',
    'to': '/clients',
  },
  {
    'name': 'Services',
    'to': '/services',
  },
  {
    'name': 'Contact',
    'to': '/contact',
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
const abs_contact = [
  {
    'name': 'info@shinebhola',
    'link': 'mailto:info@shinebhola',
  },
  {
    'name': '+91-941-422-7723',
    'link': 'tel:+91-941-422-7723',
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
}</style>