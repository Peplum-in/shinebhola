<template>
    <div class="animate__animated animate__fadeIn">

        <div class=" is-hidden-touch pt-4">
            <div class="has-text-white">
                <p class="heading">CONTACT</p>
                <ul class="">
                    <li><a href="mailto:info@shinebhola.com"
                            class="is-size-5-desktop is-is-size-6-touch is-size-6 has-text-white">info@shinebhola.com</a>
                    </li>
                    <li><a href="tel:919414227723"
                            class="is-size-6  is-size-5-desktop is-is-size-6-touch has-text-white">+91-9414227723</a></li>
                </ul>

                <div v-if="submit_error" class=" my-6 py-6 animate__animated animate__fadeIn">
                    <hr width="30%" class="shine-hr">
                    <p class="is-size-5-desktop is-is-size-6-touch ">

                        It seems we are having some error to pass on your message. <br>
                        Please try contacting us directly.
                    </p>

                    <button class="button mt-5 button-shine">Back to Home</button>
                </div>
                <div v-if="submit_success" class=" my-6 py-6 animate__animated animate__fadeIn">

                    <p class="is-size-5-desktop is-is-size-6-touch ">

                        Thank you for your message. <br> We'll get back to you shortly.

                    </p>

                    <button class="button mt-5 button-shine">Back to Home</button>
                </div>
                <div>
                    <div class="columns mt-2">
                        <div class="column is-5-desktop">

                            <p class="is-size-5-desktop is-is-size-6-touch">
                                Tell us about your project or just say hello!
                                Drop us a line.</p>
                            <br>
                            <form @submit.prevent="sendMessage" name="gform" data-email="peplumshine@gmail.com">

                                <div class="field">
                                    <label for="name" class="label">Name*</label>
                                    <input class="input" name="name" required placeholder="Enter your name"> <br>
                                </div>
                                <div class="field">
                                    <label for="email" class="has-text-whtie label">E-Mail*</label>
                                    <input class="input" name="email" type="email" required
                                        placeholder="Enter your e-mail ID">
                                </div>
                                <div class="field">
                                    <label for="subject" class="label">Subject*</label>
                                    <input class="input" name="subject" required placeholder="Enter subject">
                                </div>
                                <div class="field">
                                    <label for="message" class="label">Message</label>
                                    <textarea class="textarea" name="message" placeholder="Enter your message"
                                        type="text"></textarea>
                                </div>
                                <button :disabled="is_submit" class="button  button-shine" type="submit">Send </button>

                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class=" is-hidden-desktop section pt-0">
            <div class="has-text-white">
                <p class="heading">CONTACT</p>
                <ul class="">

                    <li><a href="mailto:info@shinebhola.com"
                            class="is-size-5-desktop is-is-size-6-touch is-size-6 has-text-white">info@shinebhola.com</a>
                    </li>
                    <li><a href="tel:919414227723"
                            class="is-size-6  is-size-5-desktop is-is-size-6-touch has-text-white">+91-9414227723</a></li>


                </ul>

                <div v-if="submit_success" class="animate_animate animate_fadeIn">
                    <p class="is-size-5-desktop is-is-size-6-touch">

                        Thank you for your message. We'll get back to you shortly.

                    </p>
                </div>
                <form v-else @submit.prevent="sendMessage" name="gform" data-email="peplumshine@gmail.com">
                    <div class="columns mt-2">
                        <div class="column is-5-desktop">

                            <p class="is-size-5-desktop is-is-size-6-touch">
                                Tell us about your project or just say hello!
                                Drop us a line.</p>
                            <br>

                            <div class="field">
                                <label for="name" class="label">Name*</label>
                                <input class="input has-text-white" name="name" required placeholder="Enter your name"> <br>
                            </div>
                            <div class="field">
                                <label for="email" class="label">E-Mail*</label>
                                <input class="input" name="email" type="email" required placeholder="Enter your e-mail">
                            </div>
                            <div class="field">
                                <label for="subject" class="label">Subject*</label>
                                <input class="input" name="subject" required placeholder="Enter subject">
                            </div>
                            <div class="field">
                                <label for="message" class="label">Message</label>
                                <textarea class="textarea" name="message" placeholder="Enter your message"
                                    type="text"></textarea>

                            </div>

                            <button type="submit" class="button  mt-5 button-shine is-fullwidth ">Send</button>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script setup>

let submit_success = ref(false);
let submit_error = ref(false);
let is_submit = ref(false);
// const form = {         b
//     name: null,
//     email: null,
//     subject: null,
//     message: null,
// }

function sendMessage() {
    const form = document.forms["gform"];
    // Gmail - Spreadsheet integration

    const scriptURL = 'https://script.google.com/macros/s/AKfycbwTF5G2DYc_YkH4vwmqorTPTl9i1UH__wSDUllAaXbI_z2ceWVhdOlYz_yMV3DIStcO_g/exec'
    is_submit.value = true
    const { data_check } = $fetch(scriptURL, { method: 'POST', body: new FormData(form) })
        .then(response => {
            console.log(response)
            if (response.result == 'success') {
                submit_success.value = true
            }
            else {
                submit_error.value = true
            }
        })
        .catch(error => {
            submit_error.value = true

            console.error('Error!', error.message)
        }
        ).finally(() => {
            is_submit.value = true

        })
}


</script>

<style></style>