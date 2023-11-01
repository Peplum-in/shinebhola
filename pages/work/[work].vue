<template>
    <div>

        <div>

            <div class="section py-0 mb-4 is-hidden-desktop has-text-white  is-rounded ">
                <div class="level is-mobile ">

                    <div class="level-left has-text-light">

                        {{ text_string }}
                    </div>

                </div>
            </div>
            <div class=" py-0 mb-4 animate_animated animate_fadeIn is-hidden-touch has-text-white  is-rounded ">
                <div class="level is-mobile ">
                    <div class="level-left ">

                        <!-- <div class="level-item  ">

                            {{ text_string }}
                        </div> -->
                        <nuxt-link v-for="(nav, index) in navigation" :key="index" :to="'/work/' + nav.link_text"
                            class="level-item has-text-white is-capitalized "
                            :class="{ 'has-hover has-text-grey': route.params.work != nav.link_text }">

                            {{ nav.link_text }}
                        </nuxt-link>
                    </div>

                </div>
            </div>

            <div class="masonry ">

                <div class="brick animate__animated animate__fadeInUp" :key="index + 'images_item'"
                    v-for="(row, index) in work">
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

        </div>
    </div>
</template>
<script setup>
const route = useRoute();
function getCapitalizedText(text) {
    return text[0].toUpperCase() + text.substring(1)
}
const photo_string = getCapitalizedText(route.params.work);
const text_string = getCapitalizedText(route.params.work);
const { data: navigation } = await useAsyncData('navigation', () => queryContent('/nav').only(['title', 'link_text']).find());

const { data: work } = await useAsyncData('work', () => queryContent('/work').where({ 'tag': route.params.work }).find())
// const { data: page } = await useAsyncData('nav', () => queryContent('/nav').where({ 'title': photo_string }).find())
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
</script>


<style>
a.has-hover {
    transition: 0.2s all ease-in;
    color: #666666!important
}

a.has-hover:hover {
    color: lightgrey !important
}
</style>
