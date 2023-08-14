<template>
    <div v-if="work">

        <div class="section py-0 mb-4 is-hidden-desktop has-text-white  is-rounded ">
            <div class="level is-mobile ">
                <nuxt-link to="/work" class="level-left button-shine-light has-text-grey-light">
                    ← All
                </nuxt-link>
                <div class="level-right has-text-light">

                    {{ text_string }}
                </div>
            </div>
        </div>
        <div class=" py-0 mb-4 is-hidden-touch has-text-white  is-rounded ">
            <div class="level is-mobile ">
                <div class="level-left has-text-light">
                    <nuxt-link to="/work" class="level-item  has-text-grey-light">
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

                    <figure class="image  has-background-dark">
                        <nuxt-picture provider="netlify" sizes="sm:100vw md:50vw lg:600px" format="webp" width="400"
                            placeholder quality="80" loading="lazy" :src="row.image" />
                    </figure>
                    <div class=" mt-1 mb-4">
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
const { data: work } = await useAsyncData('work', () => queryContent('/work').only(['image']).where({ 'tag': route.params.work }).find())
// const { data: page } = await useAsyncData('nav', () => queryContent('/nav').where({ 'title': photo_string }).find())


</script>
