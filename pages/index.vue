<template>
    <div>
        <div class="masonry ">

            <!-- {{  }} -->
            <div class="brick  animate__animated animate__fadeInUp " :key="index + 'images_item'"
                v-for="(row, index) in work">
                <div class="image-mason ">

                    <figure class="image has-background-black">
                        <img :src="cldImage(row.image)" alt="">
                    </figure>
                    <div class=" mt-1 mb-4">
                    </div>
                </div>
            </div>



        </div>
        <div class="my-6"></div>

        <div class="is-hidden-touch pt-6 has-text-white">


            <div class="columns has-text-white  mb-6 is-variable is-8 is-multiline">
                <div class="column is-6">
                    <p class="heading">
                        ABOUT US</p>
                    <p class="is-size-6">
                        Meet Shine Bhola, an architect, an academician and a photographer. Graduated as an architect from
                        MNIT Jaipur and MFA in Photography from NID Ahmedabad and UCA Farnham, United Kingdom in 2010.

                        <br>
                        In 2011, he established Shine Bhola Studios in Jaipur and is living his passion since then.
                    </p>

                </div>

                <div class="column is-4 is-offset-2-desktop">



                    <p class="heading">
                        INFO</p>
                    <p class=" ">

                    <ul>


                        <li><a href="mailto:info@shinebhola.com" class=" is-size-6 has-text-white">info@shinebhola.com</a>
                        </li>
                        <li><a href="tel:917073077042" class="is-size-6  has-text-white">+91-7073077042</a></li>
                        <li class="">Facebook-<a href="" class="is-size-6 has-text-white  is-underlined">@shinebhola</a>
                        </li>
                        <li class="">Instagram-
                            <a href="" class="is-size-6 has-text-white  is-underlined">@shinebhola</a>
                        </li>
                    </ul>


                    </p>


                </div>


            </div>
            <div class="mt-6 has-text-white">

                <p class="heading has-text-centered">
                    CLIENTS</p>


                <div class="columns is-centered is-variable is-8 is-multiline">
                    <div class="column is-2 " v-for="(row, index) in clients_list" :key="index + '_client'">
                        <figure class="image is-1by1  ">
                            <nuxt-picture  :alt="'Photography for ' + row.name + ' by Shine Bhola'"
                                sizes="sm:100vw md:50vw lg:600px" format="webp" width="400" placeholder quality="80"
                                loading="lazy" :src="row.image" />
                        </figure>
                    </div>
                </div>


            </div>

        </div>
        <div class="is-hidden-desktop section py-0">

            <div class=" has-text-white  mb-6 ">
                <div class="mt-6">
                    <p class="heading">
                        ABOUT US</p>
                    <p class="is-size-6">
                        Meet Shine Bhola, an architect, an academician and a photographer. Graduated as an architect from
                        MNIT Jaipur and MFA in Photography from NID Ahmedabad and UCA Farnham, United Kingdom in 2010.

                        <br>
                        In 2011, he established Shine Bhola Studios in Jaipur and is living his passion since then.
                    </p>

                </div>

                <div class="mt-6">



                    <p class="heading">
                        INFO</p>
                    <p class=" ">

                    <ul>


                        <li><a href="mailto:info@shinebhola.com" class=" is-size-6 has-text-white">info@shinebhola.com</a>
                        </li>
                        <li><a href="tel:917073077042" class="is-size-6  has-text-white">+91-7073077042</a></li>
                        <li class="">Facebook-<a href="" class="is-size-6 has-text-white  is-underlined">@shinebhola</a>
                        </li>
                        <li class="">Instagram-
                            <a href="" class="is-size-6 has-text-white  is-underlined">@shinebhola</a>
                        </li>
                    </ul>


                    </p>


                </div>
                <div class="mt-6">

                    <p class="heading">
                        CLIENTS</p>
                    <div class="columns is-mobile is-centered is-variable is-8 is-multiline">
                        <div class="column  is-4-touch " v-for="(row, index) in clients_list" :key="index + '_client'">
                            <figure class="image is-1by1  ">
                                <nuxt-picture  :alt="'Photography for ' + row.name + ' by Shine Bhola'"
                                    sizes="sm:100vw md:50vw lg:600px" format="webp" width="400" placeholder quality="80"
                                    loading="lazy" :src="row.image" />
                            </figure>
                        </div>
                    </div>


                </div>


            </div>
        </div>


    </div>
</template>
<script setup>

function cldImage(link){
    
    const x = link.split('/upload')
    const z = x[0]+'/upload/f_webp,q_80,w_600,dpr_auto/'
    const final = z+x[1]
    return final
}

const { data: work } = await useAsyncData('work', () => queryContent('/work').only(['image', 'caption']).find())

const clients_list = [
    {
        'name': 'BBC',
        'image': '/resized/bbc.png',
    },
    {
        'name': 'Conde Nast',
        'image': '/resized/condenast.png',
    },
    {
        'name': 'Good Earth',
        'image': '/resized/goodearth.png',
    },
    {
        'name': 'Enrico',
        'image': '/resized/enrico.png',
    },
    {
        'name': 'Mitsubishi Electric',
        'image': '/resized/mitsubishi.png',
    },
    {
        'name': 'Opame',
        'image': '/resized/opame.png',
    },
    {
        'name': 'Nila House',
        'image': '/resized/nilahouse.png',
    },
    {
        'name': 'Whirlpool',
        'image': '/resized/whirlpool.png',
    },
]
</script>


<style>
.upper-bar {
    border-top: 0.5px solid #fefefe70;
    margin-top: 1.5rem;
    padding-top: 0.8rem;
}
</style>