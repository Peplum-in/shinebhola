<template>
    <div>
        <section class="is-hidden-touch py-0">
            <div class="columns">
                <div class=" column has-text-white is-5-desktop ">
                    <figure class="animate__animated animate__fadeInUp is-hidden-desktop image is-4by5 mb-6">
                        <img src="/img/shineshine.jpg" class="has-background-dark" alt="" />
                    </figure>

                    <div class="animate__animated animate__fadeIn">

                        <p class="heading mt-4">
                            ABOUT</p>
                        <p class=" has-text-white is-size-5-desktop is-size-6-touch">
                            Meet Shine Bhola, an architect, an academician and a photographer. Graduated as an architect
                            from
                            MNIT Jaipur and MFA in Photography from NID Ahmedabad and UCA Farnham, United Kingdom in 2010.
                            <br>

                            In 2011, he established Shine Bhola Studios in Jaipur and is living his passion since then.
                        </p>
                        <div class="mt-5">

                            <p class="heading">
                                OUR BELIEF</p>
                            <p class="is-size-5-desktop is-size-6-touch">
                                The best way to describe his approach: ‘My true passion for photography is in its power to
                                fascinate and teach new lessons every day! I capture what I feel and feeling is my inner
                                belief.’ If that’s all you ever know about him, it’s enough to say you know him very, very
                                well
                                !


                            </p>

                            <p class="heading mt-5">
                                OUR WORK</p>
                            <p class=" is-size-5-desktop is-size-6-touch ">

                                His work spans from landscape, architecture, portraits, product, fashion and conceptual
                                photography. And to share his knowledge of perfect frames, he is a faculty at most of the
                                prestigious colleges of Jaipur, namely, Aayojan School of Architecture, ICG, IICD, MNIT and
                                has
                                conducted workshop for IIID.


                            </p>

                        </div>

                    </div>
                </div>
                <div class="column is-6 is-offset-1-desktop is-hidden-touch">
                    <figure class="animate__animated animate__fadeInUp image is-4by5 mt-5 ">
                        <img src="/img/shineshine.jpg" class="has-background-dark" alt="" />
                    </figure>
                </div>
                <br>


            </div>




        </section>
        <figure class="animate__animated animate__fadeIn is-hidden-desktop image is-4by5 ">
            <img src="/img/shineshine.jpg" class="has-background-dark" alt="" />
        </figure>
        <section class="is-hidden-desktop section ">
            <div class="columns">
                <div class="animate__animated animate__fadeIn column has-text-white is-5-desktop ">
                    <p class="heading">
                        ABOUT</p>
                    <p class="has-text-white is-size-5-desktop is-size-6-touch">
                        Meet Shine Bhola, an architect, an academician and a photographer. Graduated as an architect from
                        MNIT Jaipur and MFA in Photography from NID Ahmedabad and UCA Farnham, United Kingdom in 2010.
                        <br>
                        <br>
                        In 2011, he established Shine Bhola Studios in Jaipur and is living his passion since then.
                    </p>
                    <div class="">

                        <p class="heading  mt-5">
                            OUR BELIEF</p>
                        <p class="is-size-5-desktop is-size-6-touch">
                            The best way to describe his approach: ‘My true passion for photography is in its power to
                            fascinate and teach new lessons every day! I capture what I feel and feeling is my inner
                            belief.’ If that’s all you ever know about him, it’s enough to say you know him very, very well
                            !


                        </p>

                        <p class="heading mt-5">
                            OUR WORK</p>
                        <p class=" is-size-5-desktop is-size-6-touch ">

                            His work spans from landscape, architecture, portraits, product, fashion and conceptual
                            photography. And to share his knowledge of perfect frames, he is a faculty at most of the
                            prestigious colleges of Jaipur, namely, Aayojan School of Architecture, ICG, IICD, MNIT and has
                            conducted workshop for IIID.


                        </p>

                    </div>

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
}</style>