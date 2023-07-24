<template>
    <div>

        <p class="heading ">Work Page - Need more content</p>
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
const { data: work } = await useAsyncData('work', () => queryContent('/work').only(['image', 'caption']).find())


</script>