<template>
    <div class="">
        <div class="">
            <p class="heading">CONTACT</p>
            <ul>


                <li><a href="mailto:info@shinebhola.com" class=" is-size-6 has-text-dark">info@shinebhola.com</a></li>
                <li><a href="tel:917073077042" class="is-size-6  has-text-dark">+91-7073077042</a></li>
                <li class="">Facebook-<a href="" class="is-size-6 has-text-dark  is-underlined">@shinebhola</a>
                </li>
                <li class="">Instagram-
                    <a href="" class="is-size-6 has-text-dark  is-underlined">@shinebhola</a>
                </li>
            </ul>
            <br>
            <p class="is-size-5-desktop is-is-size-6-touch mb-6">
                Tell us about your project or just say hello!

                Drop us a line.</p>

            <form class="" @submit="sendMessage()">
                <div class="columns">
                    <div class="column is-5-desktop">

                        <div class="field">
                            <label for="name" class="label">Name*</label>
                            <input class="input" name="name" required placeholder="Enter your Name"> <br>
                        </div>
                        <div class="field">
                            <label for="email" class="label">E-Mail*</label>
                            <input class="input" name="email" type="email" required placeholder="Enter your Name">
                        </div>
                        <div class="field">
                            <label for="subject" class="label">Subject*</label>
                            <input class="input" name="subject" required placeholder="Enter your Name">
                        </div>
                        <div class="field">
                            <label for="message" class="label">Mesage*</label>
                            <input class="input" name="message" required placeholder="Enter your Name">
                        </div>

                        <button class="button is-link">Send message</button>
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
function sendMessage() {
    // Gmail - Spreadsheet integration
}
</script>

<style></style>