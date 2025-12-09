<template>
    <div class="header">
        <div class="header__container">
            <div class="logo">
                <img src="@/assets/images/logo.png" alt="logo"></img>
            </div>
            <div class="header__nav">
                <button class="nav__button nav__button-content">
                    About Us
                </button>
                <button class="nav__button nav__button-content">
                    Web3ATL
                </button>
                <button class="nav__button nav__button-content">
                    Accelerator
                </button>
                <button class="nav__button nav__button-content">
                    Blog
                </button>
                <button class="nav__button nav__button-content">
                    Contact
                </button>
            </div>
        </div>
    </div>
</template>

<script lang="ts"></script>

<style scoped>

.header {
    padding: 62px 60px 0 60px;
    display: flex;
    justify-content: center;
}

.header__container {
    max-width: 1320px;
    width: 100%;
    display: flex;
    justify-content: space-between;
}

.header__nav {
    display: flex;
    gap: 30px;
}

.nav__button {
    background: none;
    border: none;
}

.nav__button-content {
    color: var(--main-text);
    font-size: 1rem;
    font-weight: 500; /* Я думаю что тут 500, но в фигме 600*/ 
}

.nav__button:hover {
    scale: 1.1;
    transition: all 0.5s ease;
}

</style>