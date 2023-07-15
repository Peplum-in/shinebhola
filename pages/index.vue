<template>
    <div>
        <div class="columns">
            <div class="column is-8-desktop">

                <p class="title is-size-4">

                    Product Photography
                </p>
                <p class="subtitle is-size-6">
                    The products are the static entities that I see and work with every day. To be significant, products are
                    objects
                    that we want to touch and feel rather seeing them in images. For this reason, I always add a story
                    behind
                    every
                    product I work with.

                </p>
            </div>
        </div>
        <br>
        <div class="columns is-multiline">
            <div class="column is-3-desktop" v-for="(row,index) in work" :key="index+'_work'+row.title">
                <figure class="image is-4by5">
                    <nuxt-img :src="row.image" class="has-background-warning" provider="netlify" loading="lazy" format="webp" sizes="sm:100vw md:50vw lg:800px" />
                    <!-- <img src="" class="has-background-warning" alt=""> -->
                </figure>
                <p class="mt-2 caption">{{ row.caption }}</p>
            </div>
        </div>
    </div>
</template>
<script setup>
const { data: work } = await useAsyncData('work', () => queryContent('/work').only(['image', 'caption']).find())


</script>