<script setup>
import ModalPopup from "./ModalPopup.vue";

const menuItems = [
    {
        name: 'Подобрать решение',
        icon: 'search',
        href: 'catalog'
    },
    {
        name: 'О нас',
        icon: 'plane',
        href: 'about'
    },
    {
        name: 'Галерея',
        icon: 'gallery',
        href: 'gallery'
    },
    {
        name: 'Ипотека',
        icon: 'bank',
        href: 'mortgage'
    },
    {
        name: 'Контакты',
        icon: 'call',
        href: 'contact'
    }
]
</script>

<template>
    <header class="flex gap-3.5 items-center p-5 tracking-[-0.45px] leading-none">
        <div class="grid gap-2.5 flex-1">
            <img src="/images/logo.svg" width="100" alt="">
            <slot />
        </div>

        <ModalPopup title="Меню">
            <template v-slot:default="{onClick}">
                <button
                    class="border border-(--border) rounded-full px-[15px] py-[6px]"
                    @click="onClick"
                >
                    <img src="/images/menu.svg" width="24" alt="">
                </button>
            </template>

            <template #body>
                <a
                    v-for="(item, index) in menuItems"
                    :key="index"
                    :href="`#/${item.href}`"
                    class="flex items-center gap-2.5 px-8 py-5.5 text-[14px]/[22px] font-light tracking-[-0.4px]"
                >
                    <img :src="`images/menu-${item.icon}.svg`" width="15" alt="">
                    <span>{{ item.name }}</span>
                </a>

                <div class="flex items-center gap-5 bg-[#F9F9F9] rounded-[15px] px-5 py-4 mx-4">
                    <div class="w-[48px] h-[48px] bg-[url(/images/modyl-logo.svg)] bg-size-[85%] bg-position-[center_25%] bg-no-repeat rounded-full border border-black"></div>

                    <div>
                        <div class="text-[14px]/[22px] text-[#545452] font-medium">Аккредитованный застройщик</div>
                        <div class="text-[12px]/[16px]">Работаем с Эскроу</div>
                    </div>
                </div>

                <div class="px-8 py-6 text-[12px]/[20px] text-black/60 font-light tracking-[-0.4px]">
                    <a href="mailto:modyl.info@gmail.com" class="underline">modyl.info@gmail.com</a> <br>
                    График работы: <br>
                    <a href="tel:+73432130605" class="underline">8 (343) 213-06-05</a> <br>
                    Пн-сб: с 09:00 до 19:00 <br>
                    <br>
                    © Все права защищены <br>
                    ИНН: 6679148463
                    КПП: 667901001
                    ОГРН: 1226600002683
                </div>
            </template>
        </ModalPopup>
    </header>
</template>

<style scoped>

</style>
