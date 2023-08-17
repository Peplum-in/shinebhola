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
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279273/bbc_sf6bbr.png',
    },
    {
        'name': 'Conde Nast',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279274/condenast_ibqqdn.png',
    },
    {
        'name': 'Good Earth',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279274/goodearth_i4ufqf.png',
    },
    {
        'name': 'Enrico',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279274/enrico_nnw9lm.png',
    },
    {
        'name': 'Mitsubishi Electric',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279274/mitsubishi_vwcjuz.png',
    },
    {
        'name': 'Opame',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279273/opame_yysify.png',
    },
    {
        'name': 'Nila House',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279274/nilahouse_x6x5x8.png',
    },
    {
        'name': 'Whirlpool',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_512/v1692279274/whirlpool_liokqr.png',
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