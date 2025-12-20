<script setup>
import ModalPopup from "./ModalPopup.vue";

const props = defineProps({
    data: Object,
});
</script>

<template>
    <div class="px-4 py-5 rounded-[20px] shadow-[1px_7px_20px_#00000026]">
        <div class="flex gap-2 overflow-auto no-scrollbar snap-x snap-mandatory">
            <img
                v-for="(image, index) in data.images"
                :key="index"
                :src="image"
                alt=""
                class="w-[280px] h-[220px] object-cover rounded-[10px] snap-center"
            >
        </div>

        <div class="grid gap-3 p-4 pr-0 mt-3">
            <div class="text-[22px]/[28px] font-semibold tracking-[0.35px]">
                {{ data.name }}
            </div>

            <div class="flex gap-4 items-center text-[15px]/[20px] tracking-[-0.23px]">
                <div class="rounded-full px-4 py-2 border border-[#BFBFBF]">
                    {{ data.category }}
                </div>

                <div class="flex gap-1.5 items-center">
                    <img src="/images/ruler.svg" width="20" alt="">
                    <span>{{ data.area }} кв.м</span>
                </div>

                <div class="flex gap-1.5 items-center">
                    <img src="/images/layers.svg" width="20" alt="">
                    <span>{{ data.modules }} модуля</span>
                </div>
            </div>

            <ul class="list-disc list-inside py-2.5 text-(--dim) text-[17px]/[22px] tracking-[-0.4px]">
                <li
                    v-for="(line, index) in data.description"
                    :key="index"
                >
                    {{ line }}
                </li>
            </ul>

            <div class="text-[30px]/1 tracking-[-0.45px] py-4">
                <span class="font-semibold">
                    {{ data.price.toLocaleString('ru') }}
                </span> ₽
            </div>

            <ModalPopup>
                <template v-slot:default="{onClick}">
                    <div
                        class="flex gap-4 px-1 pt-3"
                        @click="onClick"
                    >
                        <button class="flex-1 bg-(--button) rounded-full px-4 py-2.5 font-light text-[14px]/[22px] tracking-[-0.45px]">Позвоните мне</button>
                        <button class="flex-1 bg-(--button) rounded-full px-4 py-2.5 font-light text-[14px]/[22px] tracking-[-0.45px]">Хочу заказать</button>
                    </div>
                </template>

                <template #header>
                    <div class="flex items-center gap-2.5">
                        <img
                            class="w-[40px] h-[40px] rounded-[10px] object-cover"
                            :src="data.images[0]"
                            alt=""
                        >
                        <div class="tracking-[-0.45px]">
                            <div class="text-[12px]">Вас интересует:</div>
                            <div class="text-[14px] font-medium">{{ data.name }}</div>
                        </div>
                    </div>
                </template>

                <template #body>
                    <div class="grid gap-5 p-4">
                        <div class="text-[20px]/[28px] font-semibold tracking-[0.35px]">Ответим на все интересующие вопросы, найдём лучшую цену</div>

                        <form action="" class="grid gap-5 py-2.5">
                            <input type="tel" placeholder="Ваш телефон" class="font-light text-sm/[22px] bg-(--select) rounded-[20px] px-4 py-3 tracking-[-0.45px] no-spinner">

                            <div class="flex items-start gap-2.5">
                                <input type="checkbox" required class="appearance-none w-[20px] h-[20px] bg-[#F3F2F2] rounded-full shrink-0">
                                <span class="text-[12px]/[16px] text-(--dim) tracking-[-0.4px]">Отправляя заявку, даю своё согласие на сбор <a href="#" class="text-(--link)">и обработку персональных данных, принимаю пользовательское соглашение</a></span>
                            </div>

                            <button class="bg-(--button) rounded-full px-10 py-2.5 text-[14px]/[22px] font-light tracking-[-0.45px] opacity-60">
                                Жду звонка
                            </button>
                        </form>

                        <div class="bg-[#A1A1A1] rounded-full h-[5px] mx-4"></div>

                        <div class="text-[18px]/[28px] font-semibold tracking-[0.35px] text-center">Не хотите ждать? Свяжитесь с нами</div>
                    </div>

                    <div class="flex items-center gap-4.5 px-5 py-3">
                        <a href="tel:+79941450050" class="text-center bg-(--button) rounded-full flex-1 py-2.5 text-[16px]/[22px] font-semibold">8 994 145-00-50</a>

                        <div class="flex gap-1">
                            <button class="border border-(--button)/50 rounded-full p-3.5">
                                <img src="/images/telegram-gray.svg" alt="">
                            </button>
                            <button class="border border-(--button)/50 rounded-full p-3.5">
                                <img src="/images/whatsapp-gray.svg" alt="">
                            </button>
                        </div>
                    </div>
                </template>
            </ModalPopup>
        </div>
    </div>
</template>

<style scoped>

</style>
