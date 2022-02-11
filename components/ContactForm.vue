<template>
    <form name="Contact Form" class="contact-form" netlify method="POST">
        <input type="hidden" name="form-name" value="Contact Form" />
        <div class="contact-form__wrapper">
            <input placeholder="Name" class="contact-form__input" type="text" name="name">
            <label class="contact-form__label" for="name"></label>

            <input placeholder="Email" class="contact-form__input" type="email" name="email">
            <label class="contact-form__label" for="email"></label>

            <input placeholder="Subject" class="contact-form__input" type="text" name="subject">
            <label class="contact-form__label" for="subject"></label>

            <textarea placeholder="Message" class="contact-form__input" name="body" rows="10" />
            <label class="contact-form__label" for="body"></label>
        </div>
        <button class="contact-form__btn btn--orange btn--outline" >Launch</button>
    </form>
</template>

<style lang="scss" scoped>
    @import '~/assets/css/forms';
</style>