<template>
  <div class="section py-5 ">
    <div class="py-4 is-hidden-desktop">
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
          <li class="my-3" v-for="(nav, index) in navigation" :key="index">

            <nuxt-link  :to="nav.to"
            class="has-text-left my-3 has-text-weight-semibold pr-3">
            
            {{ nav.link_text }}
          </nuxt-link>
        </li>
          
        </ul>
      </div>
    </div>
    <div class="columns py-6-desktop pt-0">
      <div class="column is-2 is-hidden-touch ">
        <nuxt-link to="/" class="has-text-dark is-size-5">
          Company Name
        </nuxt-link>
        <p>Brings life to still shots</p>
        <br>
        <div>

          <ul>
            <li>
              <nuxt-link to="/" class="is-block has-text-dark has-text-weight-semibold pr-3">

                Home
              </nuxt-link>
              <nuxt-link v-for="(nav, index) in navigation" :key="index" :to="nav.to"
                class="is-block has-text-dark has-text-weight-semibold pr-3">

                {{ nav.link_text }}
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
      <div class="column is-12-touch ">
        <NuxtPage />

      </div>
    </div>


  </div>
</template>

<script setup>
const showMobileNav = ref(false)

const { data: navigation } = await useAsyncData('navigation', () => queryContent('/nav').only(['title', 'link_text']).find())

function showNav() {
  showMobileNav.value = !showMobileNav.value
}

const route = useRoute();

watch(route, value => {
  showMobileNav.value = false
}, { deep: true, immediate: true })

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



html {
  scroll-behavior: smooth;
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