<template>
    <form name="Contact Form" class="contact-form" netlify  method="POST">
        <div class="contact-form__wrapper">
            <!-- <label class="contact-form__label" for="name">Name:</label> -->
            <input placeholder="Name" class="contact-form__input" type="text" name="name">

            <!-- <label class="contact-form__label" for="email">Email:</label> -->
            <input placeholder="Email" class="contact-form__input" type="email" name="email">

            <!-- <label class="contact-form__label" for="subject">Subject:</label> -->
            <input placeholder="Subject" class="contact-form__input" type="text" name="subject">

            <!-- <label class="contact-form__label" for="body">Message:</label> -->
            <textarea placeholder="Message" class="contact-form__input" name="body" rows="10" />
        </div>
        <button class="contact-form__btn btn--orange btn--outline" >Launch</button>
    </form>
</template>

<style lang="scss" scoped>
    @import '~/assets/css/forms';
</style>