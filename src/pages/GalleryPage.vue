<script setup>
import Page from "../components/Page.vue";
</script>

<template>
    <Page class="grid gap-5 text-[13px]/[1.2] tracking-[-0.45px]">
        <section class="grid gap-2.5">
            <h1>Галерея</h1>
            <p class="text-(--dim)">Современный дизайн, безупречное качество и надёжность — не просто слова, а основа доступного жилья</p>
        </section>

        <img src="/images/gallery.jpg" class="h-[265px] rounded-[15px]" alt="">

        <p class="text-center font-semibold">Дом, где тепло всегда, а уют не зависит от сезона. Где можно сбежать от городской суеты и полностью расслабиться, наслаждаясь гармонией природы.</p>

        <div class="grid grid-cols-3 gap-x-2">
            <div
                v-for="(_, i) in 3"
                class="flex flex-col gap-y-3"
            >
                <img
                    v-for="j in 3"
                    :src="`images/gallery-${i * 3 + j}.png`"
                    alt=""
                >
            </div>
        </div>
    </Page>
</template>

<style scoped>

</style>
