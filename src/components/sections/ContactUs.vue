<template>
    <div class="contacts-section">
        <div class="contacts__container">
            <div class="contacts__img">
                <img :src=img_contact alt="kartinka"></img>
            </div>
            <div class="contacts__actions">
                <h1 class="section__header">Contact Us</h1>
                <div class="contact__input">
                    <div class="input__fields">
                        <input type="text" class="head__input"></input>
                        <textarea class="main__input"></textarea>
                    </div>
                    <button class="input__button input__button--content">Submit</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import img_contact from "../../assets/images/img_contact.png"
</script>

<style scoped>
.contacts-section {
    padding: 279px 120px 0 120px;
}

.contacts__container {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 163px;
}

.contacts__img {
    display: flex;
    align-items: center;
}

.contacts__actions {
    display: flex;
    flex-direction: column;
    gap: 50px;
}

.contact__input {
    display: flex;
    flex-direction: column;
    gap: 30px;
}

.input__fields {
    display: grid;
    grid-template-rows: auto auto;
    gap: 15px;
}

.head__input,
.main__input {
    height: 42px;
    border-radius: 5px;
    border: 3px solid transparent;
    background: 
        linear-gradient(#000, #000) padding-box,
        var(--gradient-dark) border-box;
    color: white;
    font-size: 1rem;
    padding: 10px 15px;
    outline: none;
    font-family: inherit;
    box-sizing: border-box;
    display: block;
}

.main__input {
    height: 221px;
}

.head__input:hover,
.main__input:hover {
    transition: all 2s ease;
    background: 
        linear-gradient(var(--bckgrnd-card, transparent), 
                        var(--bckgrnd-card, transparent)) padding-box,
                        var(--gradient-bright) border-box;
}

.input__button {
    padding: 11px 24px;
    border-radius: 8px;
    background-image: var(--gradient-dark);
    border: none;
    box-shadow: 0 17px 33px #FFFFFF33;
    cursor: pointer;
}

.input__button--content {
    font-size: 0.875rem;
    line-height: 140%;
    font-weight: 600;
    color: var(--main-text);
}

.input__button:hover {
    scale: 1.1;
    transition: 0.6s ease all;
}
</style>