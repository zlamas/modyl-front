<script setup>
import Page from "../components/Page.vue";
</script>

<template>
    <Page class="flex flex-col gap-8 px-4!">
        <template #header>
            <div class="font-bold text-2xl text-(--heading)">Здравствуйте, Иван</div>
            <div class="text-[13px] text-(--dim)">Рады видеть вас в сфере модульных решений!</div>
        </template>

        <section class="grid gap-2.5">
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
                <a href="#/catalog" class="flex flex-col justify-between bg-(--card) bg-[url(/images/card-1.png),url(/images/card-stars.png)] bg-no-repeat bg-[auto_100%,auto_45px] bg-position-[bottom,122px_13px] px-4 py-7 row-span-full rounded-[15px]">
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
        </section>

        <div class="flex items-center gap-4 bg-(--border) p-3 rounded-[15px]">
            <img src="/images/message.svg" width="40" alt="">
            <span class="font-semibold text-lg/[20px] text-white tracking-[0.35px]">О нас</span>
            <img class="ml-auto" src="/images/arrow.svg" width="20" alt="">
        </div>

        <section>
            <h2 class="mb-2.5">Лучшие предложения</h2>
            <div class="flex gap-2.5 -mx-4 px-4 overflow-auto no-scrollbar">
                <div class="flex items-center gap-3 bg-[#F9F9F9] rounded-[15px] p-3 w-[280px] shrink-0">
                    <img class="p-3 rounded-[12px] border border-(--card) bg-[#C9D2D14D]" src="/images/call.svg" alt="">

                    <div>
                        <div class="text-[14px]/[22px] text-[#384040] font-semibold">Телефон для связи:</div>
                        <div class="text-[12px]/[16px]">8 (343) 213-06-05</div>
                    </div>
                </div>

                <div class="flex items-center gap-3 bg-[#F9F9F9] rounded-[15px] p-3 w-[280px] shrink-0">
                    <img class="p-3 rounded-[12px] border border-(--card) bg-[#C9D2D14D]" src="/images/call.svg" alt="">

                    <div>
                        <div class="text-[14px]/[22px] text-[#384040] font-semibold">Телефон для связи:</div>
                        <div class="text-[12px]/[16px]">8 (343) 213-06-05</div>
                    </div>
                </div>

                <div class="flex items-center gap-3 bg-[#F9F9F9] rounded-[15px] p-3 w-[280px] shrink-0">
                    <img class="p-3 rounded-[12px] border border-(--card) bg-[#C9D2D14D]" src="/images/call.svg" alt="">

                    <div>
                        <div class="text-[14px]/[22px] text-[#384040] font-semibold">Телефон для связи:</div>
                        <div class="text-[12px]/[16px]">8 (343) 213-06-05</div>
                    </div>
                </div>

                <div class="flex items-center gap-3 bg-[#F9F9F9] rounded-[15px] p-3 w-[280px] shrink-0">
                    <img class="p-3 rounded-[12px] border border-(--card) bg-[#C9D2D14D]" src="/images/call.svg" alt="">

                    <div>
                        <div class="text-[14px]/[22px] text-[#384040] font-semibold">Телефон для связи:</div>
                        <div class="text-[12px]/[16px]">8 (343) 213-06-05</div>
                    </div>
                </div>
            </div>
        </section>

        <div class="grid gap-1 bg-[#F9F9F9] rounded-[15px] p-4">
            <img src="/images/location.svg" width="32" alt="">

            <div class="text-[18px] font-semibold">Ближайший магазин</div>
            <div class="text-[14px]">Lorem ipsum dolor sit amet consectetur adipiscing elit. Dolor sit amet consectetur adipiscing elit quisque faucibus.</div>

            <div class="flex items-center gap-4 my-3">
                <span class="font-semibold text-[16px] tracking-[0.35px]">Найти</span>
                <img src="/images/arrow-black.svg" width="16" alt="">
            </div>
        </div>

        <div class="flex items-center gap-4 bg-(--border) p-3 rounded-[15px]">
            <img src="/images/message.svg" width="40" alt="">
            <span class="font-semibold text-lg/[20px] text-white tracking-[0.35px]">О нас</span>
        </div>
    </Page>
</template>

<style scoped>

</style>
