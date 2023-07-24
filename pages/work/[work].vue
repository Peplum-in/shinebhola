<template>
    <div>
        <div class="columns">
            <div class="column is-8-desktop">

                <p class="title is-size-4">

                    {{ photo_string }} </p>
                <p class="subtitle is-size-6">
                    {{ page[0].description }}

                </p>
            </div>
        </div>
        <br>
        <div class="masonry ">

            <div class="brick animate__animated animate__fadeInUp " :key="index + 'images_item'"
                v-for="(row, index) in work">
                <div class="image-mason ">

                    <figure class="image  has-background-grey">
                        <nuxt-picture provider="netlify" sizes="sm:100vw md:50vw lg:600px" format="webp" width="400"
                            placeholder quality="80" loading="lazy" :src="row.image" />
                    </figure>

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
const photo_string = getCapitalizedText(route.params.work) + ' Photography';
const { data: work } = await useAsyncData('work', () => queryContent('/work').only(['image', 'caption']).where({ 'tag': photo_string }).find())
const { data: page } = await useAsyncData('nav', () => queryContent('/nav').where({ 'title': photo_string }).find())


</script>