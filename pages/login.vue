<template>
    <main>
        <h1>Login</h1>
        <form @submit.prevent="efetuarLogin">
            <label for="login">login</label>
            <input type="text" name="login" id="login" v-model="login">
            <label for="senha">senha</label>
            <input type="password" name="senha" id="senha" v-model="senha">
            <button type="submit">Login</button>
        </form>
    </main>
</template>

<script lang="ts">
import axios from "axios"
import { getData, setData } from 'nuxt-storage/local-storage';

export default {
    data() {
        return {
            login: "",
            senha: ""
        }
    },
    methods: {
        efetuarLogin() {
            const dados = {
                login: this.login,
                senha: this.senha
            }

            axios.post("http://localhost:8080/api/login", dados)
                .then((response) => {
                    const Token = response.data.token;

                    setData('Token', Token);

                    this.$router.push({ path: "/aulas"});
                })
                .catch((error) => {
                    console.log(error);
                })
        }
    }
}
</script>