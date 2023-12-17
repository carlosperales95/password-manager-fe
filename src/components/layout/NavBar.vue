<template>
    <header class="navbar-container">
        <h1 class="logo-name">Icon</h1>
        <ul class="nav">
            <li>
                <router-link class="nav-link" to="/about">
                    About
                </router-link>
            </li>
            <li>
                <router-link class="nav-link" to="/">
                    Home
                </router-link>
            </li>
        </ul>
    </header>
</template>

<script>
import { RouterLink } from 'vue-router';

export default {
    components: {
        RouterLink,
    },
    setup() {},
};
</script>

<style scoped>
h1 {
    margin: 0;
}

header {
    height: 3.5rem;
    width: 100%;
    padding-left: 2rem;
    padding-right: 2rem;
    font-size: 25px;
    background: rgba(19, 223, 138, 0.7);
    display: flex;
    justify-content: flex-end;
    align-items: center;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
}

.logo {
    height: 25px;
    width: 25px;
}

.logo-name,
.nav li {
    font-weight: 600;
    align-self: center;
    padding-left: 20px;
    height: inherit;
}

.nav {
    margin-left: auto;
    margin-top: 0.5rem;
    margin-bottom: 0;
    /* height: inherit; */
}

.nav li {
    display: inline-block;
    width: 6rem;
    margin: 0 10px;
    margin-bottom: 0;
    text-align: center;
}

.nav-link {
    text-decoration: none;
    color: inherit;
    padding-left: 2rem;
    padding-right: 2rem;
    padding-bottom: 0.4rem;
    text-transform: uppercase;
    transition: color 0.3s ease;
}

.nav-link:hover,
.nav-link:active {
    color: linear-gradient(45deg, #ffeb3b, #ff8c00);
    border-bottom: 4px solid rgb(10, 14, 11);
    border-radius: 5px;
}
</style>
