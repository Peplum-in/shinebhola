<template>
    <div>

        <div >
    
            <div class="section py-0 mb-4 is-hidden-desktop has-text-white  is-rounded ">
                <div class="level is-mobile ">
                    <nuxt-link to="/work" class="level-left button-shine-light">
                        All
                    </nuxt-link>
                    <div class="level-right has-text-light">
    
                        {{ text_string }}
                    </div>
                </div>
            </div>
            <div class=" py-0 mb-4 is-hidden-touch has-text-white  is-rounded ">
                <div class="level is-mobile ">
                    <div class="level-left has-text-light">
                        <nuxt-link to="/work" class="level-item">
                            ← All
                        </nuxt-link>
                        <div class="level-item ml-3">
    
                            {{ text_string }}
                        </div>
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
                                    <source :src="cldVideoBase(row.video)" type="video/webm" />
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
const { data: work } = await useAsyncData('work', () => queryContent('/work').where({ 'tag': route.params.work }).find())
// const { data: page } = await useAsyncData('nav', () => queryContent('/nav').where({ 'title': photo_string }).find())
function cldImage(link) {

    const x = link.split('/upload')
    const z = x[0] + '/upload/f_webp,q_80,w_600,dpr_auto/'
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
