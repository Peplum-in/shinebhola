<template>
    <div>
        <section class="is-hidden-touch py-0">
            <div class="columns">
                <div class=" column has-text-white is-5-desktop ">
                    <figure class="animate__animated animate__fadeInUp is-hidden-desktop image is-4by5 mb-6">
                        <img src="/img/shineshine.jpg" class="has-background-dark" alt="" />
                    </figure>

                    <p class=" has-text-white is-size-5-desktop is-size-6-touch">
                        {{ about }} </p>

                </div>
                <div class="column is-6 is-offset-1-desktop is-hidden-touch">
                    <figure class="animate__animated animate__fadeInUp image is-4by5 mt-5 ">
                        <img src="/img/shineshine.jpg" class="has-background-dark" alt="" />
                    </figure>
                </div>
                <br>


            </div>




        </section>
        <figure class="animate__animated animate__fadeIn is-hidden-desktop image is-4by5 mb-6">
            <img src="/img/shineshine.jpg" class="has-background-dark" alt="" />
        </figure>
        <section class="is-hidden-desktop section py-0">
            <div class="columns">
                <div class="animate__animated animate__fadeIn column has-text-white is-5-desktop ">
                    <p class=" has-text-white is-size-5-desktop is-size-6-touch">
                        {{ about }} </p>

                </div>
                <div class="column is-6 is-offset-1-desktop is-hidden-touch">
                    <figure class="image animate__animated animate__fadeInUp is-4by5 mt-5 ">
                        <img src="/img/shineshine.jpg" class="has-background-dark" alt="" />
                    </figure>
                </div>
                <br>


            </div>




        </section>
    </div>
</template>

<script setup>
const { data: about } = await useAsyncData('about', () => queryContent('/about').find())

</script>

<style>
figure.is-rounded {
    border-radius: 50% !important;
}

.has-background-secondary {
    background-color: #0c0c0c00;
}
</style>