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


                <form class="" @submit="sendMessage()">
                    <div class="columns mt-2">
                        <div class="column is-5-desktop">

                            <p class="is-size-5-desktop is-is-size-6-touch">
                                Tell us about your project or just say hello!
                                Drop us a line.</p>
                            <br>
                            <form action="">

                                <div class="field">
                                    <label for="name" class="label">Name*</label>
                                    <input class="input" name="name" required placeholder="Enter your name"> <br>
                                </div>
                                <div class="field">
                                    <label for="email" class="has-text-whtie label">E-Mail*</label>
                                    <input class="input" name="email" type="email" required placeholder="Enter your e-mail ID">
                                </div>
                                <div class="field">
                                    <label for="subject" class="label">Subject*</label>
                                    <input class="input" name="subject" required placeholder="Enter subject">
                                </div>
                                <div class="field">
                                    <label for="message" class="label">Message</label>
                                    <textarea class="textarea" name="message" placeholder="Enter your message" type="text"></textarea>
                                </div>

                                <button class="button  button-shine" type="submit">Send </button>
                            </form>
                        </div>
                    </div>
                </form>
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


                <form class="" @submit="sendMessage()">
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
                                <textarea class="textarea" name="message" placeholder="Enter your message" type="text"></textarea>

                            </div>

                            <button class="button  mt-5 button-shine is-fullwidth ">Send</button>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script setup>
function sendMessage() {
    // Gmail - Spreadsheet integration
}
</script>

<style></style>