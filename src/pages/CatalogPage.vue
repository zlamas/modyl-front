<script setup>
import {ref} from "vue";
import Page from "../components/Page.vue";
import SelectMenu from "../components/SelectMenu.vue";
import CatalogItem from "../components/CatalogItem.vue";
import Popover from "../components/Popover.vue";
import DoubleSlider from "../components/DoubleSlider.vue";

const types = [
    'Дома',
    'Гостевые дома',
    'Бани',
    'Хозяйственные постройки'
];

const selectedType = ref(0);

const categories = [
    'Модульные бани',
    'Модульные дома',
    'Гостевые дома',
    'Капсульные дома',
    'Гостевые комплексы',
    'Хозяйственные постройки'
];

const selectedCategory = ref(null);

const priceRange = [0, 100];

const items = [
    {
        id: 0,
        name: 'Модульный дом «Флэт 72»',
        category: 'Дома',
        area: 39,
        modules: 4,
        price: 4320000,
        description: [
            'Проект: «Flat-home»',
            'Тип проекта: Дом из четырех модулей',
            'ДxШxВ: 6000x5000x3000 мм'
        ],
        images: [
            'images/house-1.png',
            'images/house-2.png'
        ]
    },
    {
        id: 1,
        name: 'Модульный дом «Шале 30»',
        category: 'Дома',
        area: 39,
        modules: 4,
        price: 4320000,
        description: [
            'Проект: «Flat-home»',
            'Тип проекта: Дом из четырех модулей',
            'ДxШxВ: 6000x5000x3000 мм'
        ],
        images: [
            'images/house-1.png',
            'images/house-2.png'
        ]
    },
]
</script>

<template>
    <Page class="flex flex-col gap-5">
        <section>
            <h2 class="mb-2.5">Лучшие предложения</h2>
            <div class="flex gap-2.5 -mx-5 px-5 overflow-auto no-scrollbar h-[84px]">
                <img
                    v-for="i in 2"
                    :key="i"
                    class="basis-[279px] shrink-0 rounded-[15px] object-cover h-full"
                    :src="`images/offer-${i}.png`"
                    alt=""
                >
            </div>
        </section>

        <section>
            <h2 class="mb-5">Каталог</h2>
            <div class="grid grid-cols-2 gap-x-2.5 gap-y-5">
                <SelectMenu
                    title="Категория"
                    class="col-span-full"
                >
                    <div class="font-medium text-[14px]/[22px] mt-4">
                        <div
                            v-for="(category, index) in categories"
                            :key="index"
                            :class="[
                                'px-7 py-2.5',
                                { 'bg-(--button)': index === selectedCategory }
                            ]"
                            @click="selectedCategory = index"
                        >
                            {{ category }}
                        </div>
                    </div>
                </SelectMenu>

                <SelectMenu title="Стоимость, ₽">
                    <div class="grid gap-2.5 grid-cols-2 px-5 mt-4">
                        <input type="number" placeholder="Стоимость от" class="font-light text-sm/[22px] bg-(--select) rounded-[20px] px-4 py-3 tracking-[-0.45px] no-spinner">
                        <input type="number" placeholder="До" class="font-light text-sm/[22px] bg-(--select) rounded-[20px] px-4 py-3 tracking-[-0.45px] no-spinner">
                    </div>
                    <div class="px-9 py-4.5 mt-2.5">
                        <DoubleSlider :value="priceRange" />
                    </div>
                </SelectMenu>

                <SelectMenu title="Площадь" icon="ruler">
                    <div class="grid gap-2.5 grid-cols-2 px-5 mt-4">
                        <input type="number" placeholder="От, кв.м" class="font-light text-sm/[22px] bg-(--select) rounded-[20px] px-4 py-3 tracking-[-0.45px] no-spinner">
                        <input type="number" placeholder="До, кв.м" class="font-light text-sm/[22px] bg-(--select) rounded-[20px] px-4 py-3 tracking-[-0.45px] no-spinner">
                    </div>
                </SelectMenu>

                <SelectMenu title="Срок изготовления">
                </SelectMenu>

                <SelectMenu title="Кол-во модулей" icon="layers">
                    <div class="grid gap-2.5 grid-cols-2 px-5 mt-4">
                        <input type="number" placeholder="Кол-во от" class="font-light text-sm/[22px] bg-(--select) rounded-[20px] px-4 py-3 tracking-[-0.45px] no-spinner">
                        <input type="number" placeholder="До" class="font-light text-sm/[22px] bg-(--select) rounded-[20px] px-4 py-3 tracking-[-0.45px] no-spinner">
                    </div>
                </SelectMenu>

                <SelectMenu
                    title="Все фильтры"
                    multiple
                    :selected="[1]"
                />

                <div class="flex items-center gap-2.5">
                    <div class="flex gap-1 items-center font-light text-xs/[20px] tracking-[-0.45px] p-2">
                        <img src="/images/items.svg" width="16" alt="">
                        <span>
                            <span>Предложения&nbsp;</span>
                            <span class="font-medium">153</span>
                        </span>
                    </div>
                    <Popover
                        icon="images/menu.svg"
                        :items="[
                            'По площади',
                            'По возрастанию цены',
                            'По убыванию цены'
                        ]"
                    />
                </div>
            </div>
        </section>

        <div class="flex gap-3 -mx-5 px-5 overflow-auto no-scrollbar whitespace-nowrap mt-4">
            <button
                v-for="(category, index) in types"
                :key="index"
                :class="[
                    'rounded-full px-4 py-2 text-[15px]/[20px] tracking-[-0.23px] border-[#BFBFBF]',
                    {
                        'border': selectedType !== index,
                        'bg-(--button) font-medium': selectedType === index,
                    }
                ]"
                @click="selectedType = index"
            >
                {{ category }}
            </button>
        </div>

        <section>
            <div class="text-[17px]/[22px] tracking-[-0.4px] py-2.5">
                <span class="text-(--dim)">Модуль групп / </span>
                <span class="font-medium">Модульные дома </span>
            </div>

            <div class="grid gap-5 -mx-5">
                <CatalogItem
                    v-for="(item, index) in items"
                    :key="index"
                    :data="item"
                />
            </div>
        </section>
    </Page>
</template>

<style scoped>

</style>
