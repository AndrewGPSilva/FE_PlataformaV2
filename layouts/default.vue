<template>
    <header>
        <GlobalNavbar />
    </header>
    <main> 
        <InicioCategorias />
        <slot />
    </main>
    <footer>
        <GlobalRodape />
    </footer>
</template>

<style scoped>
footer {
    bottom: 0;
    position: fixed;
    width: 100%;
}
</style>