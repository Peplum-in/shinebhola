<template>
  <div id="recent-works">
    <div class="section is-hidden-desktop container my-0 py-0 py-0">
      <div class="mobile-filter ">


        <!-- <p @click="showFilterMobileNav.isOpen = !showFilterMobileNav.isOpen"
          class="pb-3 is-clickable has-text-white is-size-6">

          Filter by category
          <span v-if="!showFilterMobileNav.isOpen" class="ml-2">+</span>
          <span v-if="showFilterMobileNav.isOpen" class="ml-2">−</span>
        </p>
        <div v-show="showFilterMobileNav.isOpen">
          <p class="py-3" v-for="(nav, index) in navigation" :key="index">

            <nuxt-link @click="() => { showFilterMobileNav.isOpen = false }" :to="'/work/' + nav.link_text"
              class=" is-capitalized has-text-white  has-text-left  is-size-6 pr-3">

              {{ nav.link_text }}
            </nuxt-link>
          </p>
          <br>
        </div> -->
      </div>
    </div>
    <div class="level animate__animated animate__fadeIn px-0 is-mobile is-hidden-touch">
      <div class="level-left">
        <div class="level-item" v-for="(nav, index) in navigation" :key="index">
          <nuxt-link :to="'/work/' + nav.link_text" class=" has-hover has-text-white is-capitalized "
            :class="{ 'tag is-outlined is-dark   is-rounded': route.params.work == nav.link_text }">

            {{ nav.link_text }}
          </nuxt-link>
        </div>
      </div>
    </div>
    <section class="">
      <div class="masonry ">

        <div class="brick animate__animated animate__fadeInUp " :key="index + 'images_item'"
          v-for="(row, index) in posts">
          <div class="image-mason ">
            <div v-if="Object.keys(row).includes('video')">
              <figure class="image is-16by9 has-background-black">

                <video class="has-ratio" autoplay disablepictureinpicture loop muted playsinline
                  :poster="cldImage(row.image)" :alt="row.description">
                  <source :src="cldVideoRe(row.video)" type="video/webm" />
                  <source :src="cldVideoBase(row.video)" type="video/mp4" />
                </video>
              </figure>

            </div>
            <div v-else>

              <figure class="image has-background-black">
                <img :src="cldImage(row.image)" :alt="row.description">
              </figure>
            </div>
            <div class=" mt-1 mb-4">
            </div>
          </div>
        </div>
      </div>


    </section>

  </div>
</template>
  
<script setup>

const route = useRoute();

const showFilterMobileNav = reactive({
  isOpen: false
})

function showFilter() {
  showFilterMobileNav.isOpen = !showFilterMobileNav.isOpen
};

function cldImage(link) {

const x = link.split('/upload')
const z = x[0] + '/upload/f_webp,q_80,w_900,dpr_auto/'
const final = z + x[1]
return final
}
function cldVideoRe(link) {

const x = link.split('/upload')
const z = x[0] + '/upload/f_webm,w_600,ac_none/'
const final = z + x[1]
return final
}
function cldVideoBase(link) {

const x = link.split('/upload')
const z = x[0] + '/upload/f_mp4,w_600,ac_none/'
const final = z + x[1]
return final
}

const { data: navigation } = await useAsyncData('navigation', () => queryContent('/nav').only(['title', 'link_text']).find());

const { data: posts } = await useAsyncData('workpage', () => queryContent('/workpage').find())


</script>
  