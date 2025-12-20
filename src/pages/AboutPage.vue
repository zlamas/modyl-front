<script setup>
import Page from "../components/Page.vue";
</script>

<template>
    <Page class="grid gap-6 text-[13px]/[1.2] tracking-[-0.45px]">
        <section class="grid gap-5">
            <div class="grid gap-2.5">
                <h1>О нас</h1>
                <p class="text-(--dim)">Модуль-групп Компани ваш надежный партнер в сфере модульных решений.</p>
                <p>ОО «Модуль-групп Компани» уже более 9 лет специализируется на разработке, производстве и установке модульных строений, отвечающих самым высоким стандартам качества и эффективности. Наша миссия – обеспечить клиентов инновационными и надежными решениями. Мы стремимся быть лидерами в индустрии, предлагая уникальные конструкции, адаптированные под индивидуальные потребности каждого клиента.</p>
                <p class="font-semibold">Основные направления нашей деятельности:</p>
            </div>

            <div class="flex items-center gap-3 bg-[#F9F9F9] rounded-[15px] px-5 py-4 text-[12px]/[16px]">
                <div class="grid gap-2">
                    <img src="/images/construction.svg" width="24" alt="">
                    <span>Модульное строительство</span>
                </div>

                <div class="grid gap-2">
                    <img src="/images/measurement.svg" width="24" alt="">
                    <span>Промышленные модули</span>
                </div>

                <div class="grid gap-2">
                    <img src="/images/bolt.svg" width="24" alt="">
                    <span>Технологические решения</span>
                </div>
            </div>

            <p>Мы гордимся нашей командой специалистов, обладающих глубокими знаниями и многолетним опытом в области производства и возведения модульных зданий. Наш подход базируется на тщательном анализе потребностей клиентов, что позволяет нам предоставлять решения, полностью соответствующие их ожиданиям.</p>
        </section>

        <section class="grid gap-2.5">
            <h2>Наши модули впишутся в любую среду</h2>
            <p class="text-(--dim)">Современный дизайн, безупречное качество и надёжность — не просто слова, а основа доступного жилья</p>

            <div class="grid grid-cols-3 gap-2.5">
                <img
                    v-for="i in 6"
                    :key="i"
                    :src="`images/about-${i}.png`"
                    alt=""
                >
            </div>
        </section>

        <section class="grid gap-2.5">
            <h2>У нас вы можете купить модульный дом в ипотеку</h2>
            <p class="text-(--dim)">Аккредитованный застройщик работаем с Эскроу</p>

            <div class="grid grid-cols-3 gap-6">
                <img
                    v-for="i in 3"
                    :key="i"
                    :src="`images/bank-${i}.png`"
                    alt=""
                    class="grayscale"
                >
            </div>
        </section>
    </Page>
</template>

<style scoped>

</style>
