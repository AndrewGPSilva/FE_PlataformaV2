<template>
    <nav>
        <div class="container-titulo">
            <h1>
                <NuxtLink to="/">TI-FREE</NuxtLink>
            </h1>
        </div>
        <div class="container-links">
            <NuxtLink to="/roadmap">
                Roadmap
            </NuxtLink>
            <NuxtLink to="/cursos">
                Cursos
            </NuxtLink>
            <NuxtLink to="/login">
                Entrar
            </NuxtLink>
            <button>
                <NuxtLink to="matricula">Matricule-Se</NuxtLink>
            </button>
        </div>
    </nav>
</template>

<style scoped>
nav {
    display: flex;
    justify-content: space-between;
    padding: 15px 30px;
    background-color: #01080E;
    color: white;
    align-items: center;
}

.container-titulo {
    font-family: "Contrail One", sans-serif;
    font-weight: 400;
    font-style: normal;
    font-size: 25px;
    cursor: pointer;
}

.container-titulo a {
    color: white;
}

.container-links {
    display: flex;
    gap: 20px;
    align-items: center;
}

.container-links a {
    color: white;
    padding: 10px;
}

.container-links a:hover {
    background-color: gray;
    border-radius: 10px;
}

.container-links button {
    background-color: aqua;
    padding: 15px;
    color: black;
    font-weight: bold;
    cursor: pointer;
    border-bottom-right-radius: 20px;
    border-top-left-radius: 20px;
}

.container-links button a {
    color: black;
}

.container-links button a:hover {
    background-color: transparent;
}
</style>