<template>
  <div>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" />

    <!-- <div v-show="showMobileNav" class="blur-overlay"></div> -->
    <div class="hero  blur-overlay is-fullheight has-background-transparent" v-show="showMobileNav">
      <div class="hero-header ">
        <div class=" py-4 section container is-hidden-desktop">
          <div class="level  container is-mobile">
            <div class="level-left">
              <div class="level-item">
                <div>
                  <nuxt-link to="/" class="brandtype-mobile has-text-black ">SHINE BHOLA</nuxt-link>

                </div>
              </div>
            </div>
            <div class="level-right">
              <div class="level-item">
                <div>
                  <p @click="showNav" v-if="!showMobileNav" class="is-clickable has-text-weight-semibold has-text-dark">
                    Menu
                  </p>
                  <p @click="showNav" v-if="showMobileNav" class="is-clickable shas-text-weight-semibold has-text-dark">
                    Close
                  </p>

                </div>
              </div>
            </div>
          </div>
          <div class="mobile-nav">
            <ul>

              <li class="my-3 is-size-5">

                Home
              </li>
              <li class="my-3 is-size-5">

                Work +
              </li>
              <li class="my-3 " v-for="(nav, index) in navigation" :key="index">

                <nuxt-link :to="nav.to" class="pl-4 has-text-left my-3 is-size-5 pr-3">

                  {{ nav.link_text }}
                </nuxt-link>
              </li>
              <li class="my-3 is-size-5">

                About
              </li>
              <li class="my-3 is-size-5">

                Contact
              </li>

            </ul>
          </div>
        </div>
      </div>
      <div class="hero-footer py-4 section">
        <ul>
          <li><a href="" class="is-size-5 has-text-dark">info@shinebhola.com</a></li>
          <li><a href="" class="is-size-5 has-text-dark">+91-7073077042</a></li>
          <li><a href="" class="is-size-5 has-text-dark">Facebook</a> - <a href=""
              class="is-size-5 has-text-dark">Instagram</a></li>
        </ul>
      </div>
    </div>
    <div class=" py-4 section container is-hidden-desktop">
      <div class="level  container is-mobile">
        <div class="level-left">
          <div class="level-item">
            <div>
              <nuxt-link to="/" class="brandtype-mobile has-text-black ">SHINE BHOLA</nuxt-link>

            </div>
          </div>
        </div>
        <div class="level-right">
          <div class="level-item">
            <div>
              <p @click="showNav" v-if="!showMobileNav" class="is-clickable has-text-weight-semibold has-text-dark">Menu
              </p>
              <p @click="showNav" v-if="showMobileNav" class="is-clickable shas-text-weight-semibold has-text-dark">
                Close
              </p>

            </div>
          </div>
        </div>
      </div>
      <div class="mobile-nav" v-show="showMobileNav">
        <ul>
          <li class="my-3" v-for="(nav, index) in navigation" :key="index">

            <nuxt-link :to="nav.to" class="has-text-left my-3 has-text-weight-semibold pr-3">

              {{ nav.link_text }}
            </nuxt-link>
          </li>

        </ul>
      </div>
    </div>
    <div class="section py-5   container">

      <!-- Type 2 -->
      <div class=" is-hidden-touch ">
        <div class="section container pt-0 px-0">
          <div class="level my-0">

            <div class="level-left">
              <nuxt-link to="/" class="brandtype has-text-black ">SHINE BHOLA</nuxt-link>
            </div>
            <!-- <div class="level-item">
            </div> -->
            <div class="level-right">
              <nuxt-link to="/" class="level-item has-text-black ">Home</nuxt-link>
              <nuxt-link to="/about" class="level-item has-text-black ">About</nuxt-link>
              <nuxt-link to="/work" class="level-item has-text-black ">Work</nuxt-link>
              <nuxt-link to="/contact" class="level-item has-text-black ">Contact</nuxt-link>
            </div>
          </div>
          <div class="level mb-0 py-0">
            <div class="level-left">

              <div class="level-item" v-for="(nav, index) in navigation" :key="index">
                <nuxt-link :to="'/work/' + nav.link_text" class="is-block  pr-3 has-text-dark side-menu">

                  {{ nav.link_text }}
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="">
        <section class=" container ">
          <NuxtPage />

        </section>
      </div>


    </div>
  </div>
</template>

<script setup>
const showMobileNav = ref(true)

const { data: navigation } = await useAsyncData('navigation', () => queryContent('/nav').only(['title', 'link_text']).find());

function showNav() {
  showMobileNav.value = !showMobileNav.value
};

const route = useRoute();

watch(route, value => {
  showMobileNav.value = false
}, { deep: true, immediate: true });

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
@import url('https://fonts.googleapis.com/css2?family=Figtree:wght@300;400;500;600;700;800;900&display=swap');

* {
  font-family: 'Figtree', sans-serif;
}

html {
  background-color: #fff;
}

.brandtype {
  padding: 0 !important;
  font-size: 4rem;
  letter-spacing: 25px;
  /* animation: weights 5s linear ; */
  font-weight: 900;
}

.brandtype-mobile {
  padding: 0 !important;
  font-size: 1.7rem;
  letter-spacing: 10px;
  /* animation: weights 5s linear ; */
  font-weight: 900;
}

.page-enter-active,
.page-leave-active {
  transition: all 0.4s ease-in;
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
}

.title {
  letter-spacing: 2px;
  /* font-family: 'Moret' , 'Garamond', serif !important; */
  font-weight: normal !important;

}

.side-menu {
  letter-spacing: 1px;
  /* font-family: 'Moret', 'Garamond', serif !important; */
}

html {
  scroll-behavior: smooth;
}

.has-background-transparent {
  background-color: rgba(255, 255, 255, 0);
}

.blur-overlay {
  height: 100%;
  width: 100vw;
  position: fixed;
  /* Stay in place */
  z-index: 1;
  /* Sit on top */
  left: 0;
  top: 0;
  transition: 1s all ease;
  background-color: #fefefe;
  /* Black fallback color */
  background-color: rgba(254, 254, 254, 0.9);
  backdrop-filter: blur(4px);
  /* filter: blur(3px); */
  /* Black w/opacity */
  overflow-x: hidden;

  /* Disable horizontal scroll */
}

.overlay-content {
  position: relative;
  top: 25%;
  /* 25% from the top */
  width: 100%;
  /* 100% width */
  text-align: center;
  /* Centered text/links */
  margin-top: 30px;
  /* 30px top margin to avoid conflict with the close button on smaller screens */
}

/* Msonary */


.masonry {
  column-count: 3;
  column-gap: 27px;
}

@media (max-width: 768px) {
  .masonry {
    column-count: 1 !important;
  }
}

@media (max-width: 992px) {
  .masonry {
    column-count: 2 !important;
  }
}

@media (min-width: 1199px) {
  .masonry {
    column-count: 3 !important;
  }
}

.masonry .brick {
  box-sizing: border-box;
  /* -webkit-column-break-inside: avoid; */
  /* page-break-inside: avoid; */
  /* break-inside: avoid; */
  padding-bottom: 27px;
  /* counter-increment: 1; */
}

.masonry .image-mason {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>