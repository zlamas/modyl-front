<script setup>
import Page from "../components/Page.vue";
</script>

<template>
    <Page class="grid gap-5 text-[13px]/[1.2] tracking-[-0.45px]">
        <section class="grid gap-2.5">
            <h1>Ипотека</h1>
            <p class="text-(--dim)">У нас вы можете купить модульный дом в ипотеку</p>
        </section>

        <section class="grid gap-2.5">
            <div class="flex items-center gap-5 bg-[#F9F9F9] rounded-[15px] px-5 py-4">
                <div class="w-[48px] h-[48px] bg-[url(/images/modyl-logo.svg)] bg-size-[85%] bg-position-[center_25%] bg-no-repeat rounded-full border border-black"></div>

                <div>
                    <div class="text-[14px]/[22px] text-[#545452] font-semibold">Аккредитованный застройщик</div>
                    <div class="text-[12px]/[16px]">Работаем с Эскроу</div>
                </div>
            </div>

            <div class="grid grid-cols-3 gap-6">
                <img
                    v-for="i in 3"
                    :key="i"
                    :src="`images/bank-${i}.png`"
                    alt=""
                    class="grayscale"
                >
            </div>

            <p>ОО «Модуль-групп Компани» уже более 9 лет специализируется на разработке, производстве и установке модульных строений, отвечающих самым высоким стандартам качества и эффективности. Наша миссия – обеспечить клиентов инновационными и надежными решениями. Мы стремимся быть лидерами в индустрии, предлагая уникальные конструкции, адаптированные под индивидуальные потребности каждого клиента.</p>
        </section>
    </Page>
</template>

<style scoped>

</style>
