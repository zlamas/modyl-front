<script setup>
import Page from "../components/Page.vue";
</script>

<template>
    <Page class="grid gap-2.5 px-4!">
        <template #header>
            <div class="font-bold text-2xl text-(--heading)">Здравствуйте, Иван</div>
            <div class="text-[13px] text-(--dim)">Рады видеть вас в сфере модульных решений!</div>
        </template>

        <div>
            <div class="flex gap-2 overflow-auto no-scrollbar snap-x snap-mandatory">
                <img
                    v-for="i in 4"
                    :key="i"
                    class="rounded-[15px] snap-start"
                    src="/images/carousel.png"
                    alt=""
                >
            </div>
            <div class="flex gap-2 justify-center p-2.5">
                <button
                    v-for="i in 4"
                    :key="i"
                    class="w-[8px] h-[8px] rounded-full bg-(--bullet)">
                </button>
            </div>
        </div>

        <div class="grid grid-cols-2 grid-rows-2 gap-x-[17px] gap-y-[14px] h-[240px]">
            <a href="#/catalog" class="flex flex-col justify-between bg-(--card) bg-[url(/images/card-1.png)] bg-no-repeat bg-contain bg-bottom px-4 py-7 row-span-full rounded-[15px]">
                <div class="flex items-center gap-2">
                    <img src="/images/search.svg" width="20" alt="">
                    <span class="font-semibold text-xl text-[#4A362F] tracking-[0.35px]">Каталог</span>
                </div>
                <button class="font-medium text-xs/[20px] bg-white rounded-full px-[15px] py-[8px] tracking-[-0.23px]">Предложения 153</button>
            </a>

            <div class="bg-(--card) bg-[url(/images/card-2.png)] bg-no-repeat bg-contain bg-bottom px-4 py-2 rounded-[15px]">
                <span class="font-semibold text-lg/[20px] text-[#4A362F] tracking-[0.35px]">Гарантии</span>
            </div>

            <div class="bg-(--card) bg-[url(/images/card-3.png)] bg-no-repeat bg-contain bg-bottom px-4 py-2 rounded-[15px]">
                <span class="font-semibold text-lg/[20px] text-[#4A362F] tracking-[0.35px]">Поддержка</span>
            </div>
        </div>

        <div class="flex items-center gap-8 bg-(--border) bg-[url(/images/about.png)] bg-contain bg-right bg-no-repeat bg-blend-luminosity px-6 py-3.5 rounded-[15px]">
            <div class="flex items-center gap-2.5">
                <img src="/images/message.svg" width="20" alt="">
                <span class="font-semibold text-lg/[20px] text-white tracking-[0.35px]">О нас</span>
            </div>
            <div>
                <button class="p-2.5">
                    <img src="/images/telegram.svg" width="20" alt="">
                </button>
                <button class="p-2.5">
                    <img src="/images/whatsapp.svg" width="20" alt="">
                </button>
                <button class="p-2.5">
                    <img src="/images/vk.svg" width="20" alt="">
                </button>
            </div>
        </div>
    </Page>
</template>

<style scoped>

</style>
