<script setup>
import {computed, onMounted, ref} from "vue";
import StartPage from './pages/StartPage.vue';
import CatalogPage from "./pages/CatalogPage.vue";
import AboutPage from "./pages/AboutPage.vue";
import GalleryPage from "./pages/GalleryPage.vue";
import MortgagePage from "./pages/MortgagePage.vue";
import ContactPage from "./pages/ContactPage.vue";

const pages = {
    '/': StartPage,
    '/catalog': CatalogPage,
    '/about': AboutPage,
    '/gallery': GalleryPage,
    '/mortgage': MortgagePage,
    '/contact': ContactPage,
};

const currentPath = ref('/');
const currentPage = computed(() => pages[currentPath.value]);

onMounted(() => {
    window.location.hash = currentPath.value;

    window.addEventListener('hashchange', () => {
        currentPath.value = window.location.hash.slice(1);
    });
});
</script>

<template>
    <component :is="currentPage" />
</template>

<style scoped>

</style>
