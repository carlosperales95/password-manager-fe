<template>
    <header class="navbar-container">
        <h1 class="logo-name">Icon</h1>
        <ul class="nav">
            <li>
                <router-link
                    class="nav-link"
                    to="/about"
                >
                    About
                </router-link>
            </li>
            <li>
                <router-link
                    class="nav-link"
                    to="/"
                >
                    Home
                </router-link>
            </li>
        </ul>
    </header>
</template>

<script>
import { RouterLink } from 'vue-router'

export default {
    components: {
        RouterLink
    },
    setup() {
        
    },
}
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
    background-color: rgb(19, 223, 138);
    display: flex;
    justify-content: flex-end;
    align-items: center;
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
}

.nav {
    margin-left: auto;
}

.nav li {
    display: inline-block;
    margin: 0 10px;
}

.nav-link {
    text-decoration: none;
    color: inherit;
}

.nav-link:hover,
.nav-link:active {
    color: rgb(10, 14, 11);
}
</style>