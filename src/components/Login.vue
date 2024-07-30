<template>
    <section>
        <h1>Frame</h1>
        <div class="login-form">
            <h2>Login</h2>
            <form>
                <div class="input-form">
                    <label for="email">Email</label>
                    <input name="email" type="email" placeholder="Example@example.com" v-model="user">
                    <samp v-if="showMessge">{{ errorMesage }} </samp>
                </div>
                <div class="input-form">
                    <label for="pasword">Password</label>
                    <input name="password" type="password" placeholder="password">
                </div>
                <div>
                    <button @click.prevent="validateCredentials">
                        Login
                    </button>
                </div>
            </form>

        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'
let user = ref('');
let password = ref('');
let errorMesage = ref('');
let showMessge = ref(false)

const validateCredentials = () => {
    if (!user.value) {
        showMessge = true;
        errorMesage = "Compete este campo para iniciar sesión";
    }

}

</script>

<style scoped>
section {
    width: 800px;
    margin: auto;
}

h1 {
    font-size: 32px;
    font-weight: 200;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.login-form {
    max-width: 400px;
    border: solid 1px white;
    padding: 5px;
    border-radius: 10px;
}

.input-form {
    display: flex;
    flex-direction: column;
    justify-content: center;

}

input {
    padding: 6px;
    width: 300px;
}
</style>