<template>
  <div>
    <div class="hero  blur-overlay  is-hidden-desktop  is-fullheight-with-navbar has-background-transparent"
      v-if="showMobileNav.isOpen"
      :class="{ 'animate__animated animate__fadeIn': showMobileNav.isOpen, 'animate__animated animate__fadeOut': !showMobileNav.isOpen }">
      <div class="hero-header ">
        <div class=" py-4 section container is-hidden-desktop">

          <div class="mobile-nav mt-6 pt-6">

            <ul>

              <nuxt-link @click="() => { showMobileNav.isOpen = false }" to="/" class="my-3 has-text-white ">

                Home
              </nuxt-link>
              <li @click="showSubMobileNav.isOpen = !showSubMobileNav.isOpen"
                class="py-3 is-clickable has-text-white is-size-6">

                Work
                <span v-if="!showSubMobileNav.isOpen" class="ml-2">+</span>
                <span v-if="showSubMobileNav.isOpen" class="ml-2">−</span>
              </li>
              <div class="" v-if="showSubMobileNav.isOpen">
                <li class="py-3">

                  <nuxt-link @click="() => { showMobileNav.isOpen = false }" to="/work"
                    class="pl-6 is-capitalized has-text-white  has-text-left  is-size-6 pr-3">
                    All
                  </nuxt-link>
                </li>
                <li class="py-3" v-for="(nav, index) in navigation" :key="index">

                  <nuxt-link @click="() => { showMobileNav.isOpen = false }" :to="'/work/' + nav.link_text"
                    class="pl-6 is-capitalized has-text-white  has-text-left  is-size-6 pr-3">

                    {{ nav.link_text }}
                  </nuxt-link>
                </li>

              </div>
              <li>
                <nuxt-link @click="() => { showMobileNav.isOpen = false }" to="/about"
                  class="py-3  has-text-white  is-size-6">

                  About
                </nuxt-link>
              </li>
              <li class="mt-3">
                <a @click="() => { showMobileNav.isOpen = false }" href="https://whitegraphite.co.uk"
                  class="py-3 pt-3 has-text-white  is-size-6">

                  Studio ↗
                </a>
              </li>
              <li class="mt-3">

                <nuxt-link @click="() => { showMobileNav.isOpen = false }" to="/contact"
                  class=" has-text-white  is-size-6">

                  Contact
                </nuxt-link>
              </li>

            </ul>
          </div>
        </div>
      </div>

    </div>
    <div class=" py-4 sticky-menu section container is-hidden-desktop">
      <div class="level animate_animated animate_fadeIn mt-4 pb-0  container is-mobile sticky-menu-inner">
        <div class="level-left">
          <div class="level-item">
            <div>
              <nuxt-link to="/">

                <figure class="image " style="width:200px">
                  <img
                    src="https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400,q_100/v1692279273/shinebhola_logo_white_hetovd.png" />
                </figure>
              </nuxt-link>


            </div>
          </div>
        </div>
        <div class="level-right">
          <div class="level-item">
            <div>
              <div>
                <ul class="menu" @click="showNav" id="" :class="{ 'open': showMobileNav.isOpen }">
                  <li></li>
                  <li></li>
                  <li></li>
                </ul>


              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
    <div class=" py-5   container">

      <!-- Type 2 -->
      <div class=" is-hidden-touch ">

        <div class="section container pt-0 px-0">
          <div class="level animate_animated animate_fadeIn my-0">

            <div class="level-left">
              <nuxt-link to="/">

                <figure class="image " style="width:300px">
                  <img
                    src="https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_800,q_100/v1692279273/shinebhola_logo_white_hetovd.png" />

                </figure>
              </nuxt-link>
            </div>
            <div class="level-right">
              <nuxt-link to="/about" :class="{ 'main-item-active': route.path == '/about' }"
                class="level-item main-item has-text-white mr-5 ">About</nuxt-link>
              <nuxt-link to="/work" :class="{ 'main-item-active': route.path.includes('work') }"
                class="level-item main-item has-text-white  mr-5">Work</nuxt-link>
              <a href="https://whitegraphite.co.uk" target="blank"
                :class="{ 'main-item-active': route.path.includes('work') }"
                class="level-item main-item has-text-white  mr-5">Studio</a>
              <nuxt-link to="/contact" :class="{ 'main-item-active': route.path == '/contact' }"
                class="level-item main-item has-text-white">Contact</nuxt-link>
            </div>
          </div>

        </div>
      </div>
      <div class="">
        <section class=" container ">
          <NuxtLoadingIndicator color="white" />
          <NuxtPage class="" />
        </section>
        <footer class="section container has-background-transparent is-hidden-touch mt-6 px-0 pb-0 footer">

          <div class="level is-mobile">
            <div class="level-left">
              <div class="level-item">
                <div class="has-text-grey ">
                  <div class=" mb-2 ">
                    <a class="is-inline-block mr-4" href="https://instagram.com/shine_bhola">
                      <figure class="image is-24x24">
                        <img src="/assets/icons/instagram.svg" alt="">
                      </figure>
                    </a>
                    <a class="is-inline-block mr-4" href="mailto:info@shinebhola.com">
                      <figure class="image is-24x24">
                        <img src="/assets/icons/email.svg" alt="">
                      </figure>
                    </a>
                    <a class="is-inline-block" href="tel:919414227723">
                      <figure class="image is-24x24">
                        <img src="/assets/icons/call.svg" alt="">
                      </figure>
                    </a>

                  </div>
                  ©️2023 Shine Bhola. All Rights Reserved.
                </div>
              </div>
            </div>

          </div>
        </footer>
        <footer class="section container is-hidden-desktop has-background-transparent mt-6  pb-0 footer">

          <div class="level is-mobile">
            <div class="level-left">
              <div class="level-item">
                <div class="has-text-grey  ">
                  <div class=" mb-2 ">
                    <a class="is-inline-block mr-2" href="https://instagram.com/shine_bhola">
                      <figure class="image is-24x24">
                        <img src="/assets/icons/instagram.svg" alt="">
                      </figure>
                    </a>
                    <a class="is-inline-block mr-2" href="mailto:info@shinebhola.com">
                      <figure class="image is-24x24">
                        <img src="/assets/icons/email.svg" alt="">
                      </figure>
                    </a>
                    <a class="is-inline-block" href="tel:919414227723">
                      <figure class="image is-24x24">
                        <img src="/assets/icons/call.svg" alt="">
                      </figure>
                    </a>

                  </div>
                  ©️2023 Shine Bhola. All Rights Reserved.
                </div>
              </div>
            </div>


          </div>
        </footer>
        <div @click="scrollToTop" class="scroller is-clickable">
          <button class="scrollToTop">
            <figure class="image container is-24x24">
              <img src="/assets/icons/arrow-up.svg" alt="">
            </figure>
          </button>
        </div>
      </div>



    </div>
  </div>
</template>

<script setup>


const showMobileNav = reactive({
  isOpen: false
})
const showSubMobileNav = reactive({
  isOpen: false
})

function showNav() {
  showMobileNav.isOpen = !showMobileNav.isOpen
};
function scrollToTop() {
  window.scrollTo(0, 0);
};

const { data: navigation } = await useAsyncData('navigation', () => queryContent('/nav').only(['title', 'link_text']).find());

const route = useRoute();

watch(route, value => {
  showMobileNav.isOpen = false
}, { deep: true, immediate: true });


</script>
<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";
@import url('https://fonts.googleapis.com/css2?family=Figtree:wght@300;400;500;600;700;800;900&display=swap');

* {
  font-family: 'Figtree', sans-serif !important;
}

html {
  background-color: #0c0c0c;
  scroll-behavior: smooth;

}


.button-shine {
  border: none;
  border-radius: 0;
  transition: 0.2s all ease-in;
  padding-bottom: 3px;
  border-bottom: 1px solid #fff;
}

.button-shine-light {
  border: none;
  border-radius: 0;
  transition: 0.2s all ease-in;
  padding-bottom: 2px;
  border-bottom: 0.5px solid #ffffff7a;
}

.button-shine-two {
  border: none;
  border-radius: 0;
  transition: 0.2s all ease-in;
  padding-bottom: 4px;
  border-bottom: 0.5px solid #ffffff9a;
}

.button-shine:hover {
  transition: 0.2s all ease-in;
  /* border:none; */
  /* border-radius:0;
  padding-bottom:3px; */
  /* border-width:2px ; */
}

.brandtype {
  padding: 0 !important;
  font-size: 4rem;
  letter-spacing: 25px;
  /* animation: weights 5s linear ; */
  font-weight: 900;
}

.input {
  border-radius: 0px !important;
  background: transparent;

}

::placeholder {
  /* Chrome, Firefox, Opera, Safari 10.1+ */
  color: #fefefe !important;
  opacity: 0.4;
}

.label {
  color: white;
}

.brandtype-mobile {
  padding: 0 !important;
  font-size: 1.1rem;
  letter-spacing: 10px;
  /* animation: weights 5s linear ; */
  font-weight: 900;
}

/* .page-enter-active,
.page-leave-active {
  transition: all 0.4s ease-in;
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
} */

.title {
  letter-spacing: 2px;
  /* font-family: 'Moret' , 'Garamond', serif !important; */
  font-weight: normal !important;

}


.main-item {
  transition: 0.4s all ease-in;
}

.main-item:hover {
  border-bottom: 1px solid #0a0a0a;
  transition: 0.4s all ease-in;
}

.main-item-active {
  border-bottom: 1px solid #0a0a0a;
  transition: 0.4s all ease-in;
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
  z-index: 6;
  /* Sit on top */
  left: 0;
  top: 0;
  transition: 1s all ease;
  /* background-color: #fefefe; */
  /* Black fallback color */
  background-color: #0c0c0ce0;
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
  column-count: 2;
  column-gap: 17px;
}

@media (max-width: 768px) {
  .masonry {
    column-count: 1 !important;
  }
}

@media (min-width: 992px) {
  .masonry {
    column-count: 3;
  }
}

@media (min-width: 1199px) {
  .masonry {
    column-count: 3;
  }
}

.masonry .brick {
  box-sizing: border-box;
  -webkit-column-break-inside: avoid;
  page-break-inside: avoid;
  break-inside: avoid;
  /* counter-increment: 1; */
}

.masonry .image-mason {
  width: 100%;
  height: 100%;
  object-fit: cover;
}



.tag.is-notoutlined {
  background-color: #0c0c0c;
  text-decoration: none;
  transition: 0.2s all ease-in;
}

.tag.is-notoutlined:hover {
  background-color: rgb(240, 240, 240);
  border-radius: 9999px;
  ;

  /* text-decoration: none; */
}

a.tag:hover {
  text-decoration: none;
}

.tag.is-outlined.is-dark {

  border: 1px solid #0a0a0a;
  background-color: #0c0c0c;
  color: #0a0a0a;
  transition: 0.2s all ease-in;
}


/*  */


a#menu-icon {
  display: inline-block;
  padding: 10px;
}

a#menu-icon .bar {
  margin: 3px;
  width: 25px;
  height: 3px;
  background: #fff;
  border-radius: 0px;

  transition: margin 0.2s, transform 0.2s;

  /* same as above but with prefixes added */
  -webkit-transition: margin 0.2s, -webkit-transform 0.2s;
  transition: margin 0.2s, -webkit-transform 0.2s;
  -o-transition: margin 0.2s, transform 0.2s;
  transition: margin 0.2s, transform 0.2s;
  transition: margin 0.2s, transform 0.2s, -webkit-transform 0.2s;
}


a#menu-icon:not(.close):hover {
  padding: 6px 10px;
}

a#menu-icon:not(.close):hover .bar {
  margin: 5px 3px;
}

a#menu-icon.close .bar:first-child {
  -webkit-transform: translateY(6px) rotate(45deg);
  -ms-transform: translateY(6px) rotate(45deg);
  transform: translateY(6px) rotate(45deg);
}

a#menu-icon.close .bar:nth-child(2) {
  opacity: 0;
}

a#menu-icon.close .bar:last-child {
  -webkit-transform: translateY(-6px) rotate(-45deg);
  -ms-transform: translateY(-6px) rotate(-45deg);
  transform: translateY(-6px) rotate(-45deg);
}

/* Roudn 2 */


.menu {
  cursor: pointer;
  height: 17px;
  list-style: none;
  margin: 0;
  padding: 0;
  width: 30px;
  /* position: relative; */
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .3s ease-in-out;
  -moz-transition: .3s ease-in-out;
  -o-transition: .3s ease-in-out;
  transition: .3s ease-in-out;
}

.menu li {
  background-color: #fff;
  border-radius: 0px;
  display: block;
  height: 1px;
  left: 0;
  margin: 0;
  opacity: 1;
  padding: 0;
  position: absolute;
  width: 100%;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .15s ease-in-out;
  -moz-transition: .15s ease-in-out;
  -o-transition: .15s ease-in-out;
  transition: .15s ease-in-out;
}

.menu li:nth-child(1) {
  top: 0;
  -webkit-transform-origin: left center;
  -moz-transform-origin: left center;
  -o-transform-origin: left center;
  transform-origin: left center;
}

.menu li:nth-child(2) {
  top: 7px;
  -webkit-transform-origin: left center;
  -moz-transform-origin: left center;
  -o-transform-origin: left center;
  transform-origin: left center;
}

.menu li:nth-child(3) {
  top: 14px;
  -webkit-transform-origin: left center;
  -moz-transform-origin: left center;
  -o-transform-origin: left center;
  transform-origin: left center;
}

.menu.open li:nth-child(1) {
  left: 4px;
  top: -1px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -o-transform: rotate(45deg);
  transform: rotate(45deg);
}

.menu.open li:nth-child(2) {
  opacity: 0;
  width: 0;
}

.menu.open li:nth-child(3) {
  left: 4px;
  top: 20px;
  -webkit-transform: rotate(-45deg);
  -moz-transform: rotate(-45deg);
  -o-transform: rotate(-45deg);
  transform: rotate(-45deg);
}

/* .scroller{
  position: relative;
} */

.scrollToTop {
  background-color: #fff;
  border: none;
  border-radius: 50%;
  color: black;
  cursor: pointer;
  font-size: 16px;
  line-height: 48px;
  width: 48px;
  height: 48px;
  position: fixed;
  bottom: 30px;
  right: 30px;

  z-index: 5;
  transition: all .5s ease;
}

.scrollToTop:hover {
  transform: translateY(3px);
}

.showBtn {
  opacity: 1;
  transform: translateY(0)
}


.sticky-menu {
  position: sticky;
  top: 0px;
  z-index: 10;
  /* backdrop-filter: blur(2px); */
  backdrop-filter: blur(2px);
  mask: linear-gradient(0deg, transparent, white 0%);
  /* backdrop-filter: brightness(60%);
  backdrop-filter: contrast(40%); */
}

.sticky-menu-inner {
  position: sticky;
  /* padding-bottom:2rem; */
  z-index: 200;

}

.menu-box {
  max-height: 0;
  overflow: hidden;
  transition: all 0.2s ease-out;
}

.menu-box-open {
  max-height: 100% !important;
  transition: all 0.2s ease-out;
}
</style>