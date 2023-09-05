<template>
    <div>
        <div class="masonry ">
            <div class="brick  animate__animated animate__fadeInUp " :key="index + 'images_item'"
                v-for="(row, index) in work">
                <div class="image-mason ">
                    <div v-if="Object.keys(row).includes('video')">
                        <figure class="image is-16by9 has-background-black">

                            <video class="has-ratio" autoplay disablepictureinpicture loop muted playsinline
                                :poster="cldImage(row.image)" :alt="row.description">
                                <source :src="cldVideoRe(row.video)" type="video/webm" />
                                <source :src="cldVideoBase(row.video)" type="video/mp4" />
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
        <div class="my-6"></div>

        <div class="is-hidden-touch pt-6 has-text-white">


            <div class="columns has-text-white  mb-6 is-variable is-8 is-multiline">
                <div class="column is-12">
                    <p class="heading">
                        ABOUT US</p>
                    <p class="is-size-5-desktop">
                        Meet Shine Bhola, an architect, an academician and a photographer. <br> Graduated as an architect from
                        MNIT Jaipur and MFA in Photography from NID Ahmedabad and UCA Farnham, United Kingdom in 2010.

                        <br>
                        In 2011, he established Shine Bhola Studios in Jaipur and is living his passion since then.
                    </p>

                </div>

              


            </div>
            <div class="mt-6 has-text-white">

                <p class="heading has-text-left">
                    CLIENTS</p>


                <div class="columns is-variable is-8 is-multiline">
                    <div class="column is-2 " v-for="(row, index) in clients_list" :key="index + '_client'">
                        <figure class="image is-1by1  ">
                            <img :alt="'Photography for ' + row.name + ' by Shine Bhola'" :src="row.image" />


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

                <div class="section px-1 mt-6">

                    <p class="heading">
                        CLIENTS</p>
                    <div class="columns is-mobile is-multiline">
                        <div class="column  is-4-touch px-5 py-0 " v-for="(row, index) in clients_list" :key="index + '_client'">
                            <figure class="image is-1by1  ">
                                <img :alt="'Photography for ' + row.name + ' by Shine Bhola'" :src="row.image" />
                            </figure>
                        </div>
                    </div>


                </div>


            </div>
        </div>


    </div>
</template>
<script setup>

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

const { data: work } = await useAsyncData('work', () => queryContent('/work').find())

const clients_list = [
    {
        'name': 'BBC',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279273/bbc_sf6bbr.png',
    },
    {
        'name': 'Conde Nast',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279274/condenast_ibqqdn.png',
    },
    {
        'name': 'Good Earth',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279274/goodearth_i4ufqf.png',
    },
    {
        'name': 'Enrico',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279274/enrico_nnw9lm.png',
    },
    {
        'name': 'Mitsubishi Electric',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279274/mitsubishi_vwcjuz.png',
    },
    {
        'name': 'Opame',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279273/opame_yysify.png',
    },
    {
        'name': 'Nila House',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279274/nilahouse_x6x5x8.png',
    },
    {
        'name': 'Whirlpool',
        'image': 'https://res.cloudinary.com/dhzucwklz/image/upload/f_webp,w_400/v1692279274/whirlpool_liokqr.png',
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