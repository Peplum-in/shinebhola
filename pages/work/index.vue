<template>
    <div id="recent-works">
        {{ posts }}
        <section class=" py-6 my-6" :key="index" v-for="(row, index) in posts">
            <div class="columns">
                <div class="column is-8" :class="{ 'is-offset-4-desktop': row.shift == 'right' }">
                    <figure class="image has-background-white-bis">
                        <nuxt-img provider="netlify" loading="lazy" format="webp" sizes="sm:100vw md:50vw lg:800px" />
                    </figure>
                    <div class="columns is-centered mt-3">
                        <div class="column is-3-desktop is-12-touch">
                            <!-- <p class="title is-size-3-desktop is-size-4-touch">{{ row.title }}</p> -->
                            <!-- <p class="subtitle ">{{ row.time }}</p> -->
                        </div>
                        <div class="column is-6-desktop is-12-touch is-offset-2-desktop">
                            <!-- <p class="is-size-5-desktop is-size-6-touch">{{ row.description }}</p> -->
                            <!-- <br>
                            <nuxt-link :to="row._path"
                                class="has-text-dark has-text-weight-semibold  is-underlined is-size-5">Learn more
                                →</nuxt-link> -->
                        </div>
                    </div>
                </div>
            </div>
            <br>
            <br>
            <br>
        </section>
        <br>
        <br>
    </div>
</template>
  
<script setup>


const { data: posts } = await useAsyncData('work', () => queryContent('/work').find())


</script>
  
<style></style>