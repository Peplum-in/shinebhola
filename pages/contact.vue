<template>
    <div class="">
        <div class="">

            <p class="title is-size-4 has-text-weight-normal">
                Contact us
            </p>
            <br>
            <p class="is-size-5 mb-6">
                Tell us about your project or just say hello!

                Drop us a line.</p>
            <!-- <p class="is-size-5">In the meantime, vibe with ous to our in-house
                <a class="" href="https://music.youtube.com/channel/UCT48WYUE7S94SPTwTeljaRQ">
                    📎 mellow playlist
                </a>
            </p> -->
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