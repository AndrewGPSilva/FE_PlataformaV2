<template>
    <Head>
        <Title>
            Gpf.ev - {{ name }}
        </Title>
    </Head>
    <div>
        <h1>Aulas:</h1>
        <ul>
            <li v-for="aula in dados" :key="aula.id">
                <h2>{{ aula.titulo }}</h2>
                <p>{{ aula.descricao }}</p>
                <p>Duração: {{ aula.duracao }} minutos</p>
                <p>Status: {{ aula.status }}</p>
                <img :src="aula.imagem" alt="Imagem da aula">
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
interface Aula {
    id: number;
    titulo: string;
    descricao: string;
    duracao: number;
    imagem: string,
    status: boolean;
}

import axios from "axios";
import { getData } from 'nuxt-storage/local-storage';

export default {
    data() {
        return {
            dados: [] as Aula[],
            name: "Aulas"
        };
    },
    methods: {
        aulas() {
            const token = getData('Token');
            const headers = {
                'Authorization': `Bearer ${token}`,
            };
            axios.get("http://localhost:8080/api/dados/aulas", { headers })
                .then((response) => {
                    if (response.status === 200) {
                        this.dados = response.data['Aulas Encontradas: '];
                    } else {
                        console.error('Erro na requisição:', response.status);
                    }
                })
                .catch((error) => {
                    console.error('Erro ao obter dados:', error);
                });
        },
    },
    created() {
        this.aulas();
    },
};
</script>