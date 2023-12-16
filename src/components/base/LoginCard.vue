<template>
    <div>
        <header>
            <h2>{{title}}</h2>
        </header>
        <div class="login-row">
            <p>Username:</p><input type="text" disabled/>
        </div>
        <div class="login-row">
            <p>Password:</p><input type="text" disabled/>
        </div>
    </div>
</template>

<script>

export default {
    props: ['title', 'fields']
    // setup(_, { slots }) {
    //     const header = ref(slots['header'])
    // },
}
</script>


<style scoped>
div {
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    padding: 1rem;
    text-align: center;

}

div header {
    justify-content: space-between;
    align-items: center;
    height: 2rem;
    font-size: 12px;
}

div header h2 {
    margin-top: 0;
    border-bottom: 1px solid #ccc;
}

.login-row {
    display: flex;
    flex-flow: row;
    height: 30px;
    padding: 0.2rem;
}

.login-row p,
.login-row input {
    width: 50%;
    margin: 0;
    font-size: 20px;
    line-height: 20px;
}

.login-row input {
    height: 20px;
}
</style>