<script setup>
import ModalPopup from "./ModalPopup.vue";

const props = defineProps({
    title: String,
    multiple: Boolean,
    class: {
        type: String,
        default: ''
    }
});

const selected = defineModel('selected', {default: null});
</script>

<template>
    <ModalPopup :title="title">
        <template v-slot:default="{onClick}">
            <div
                :class="`flex items-center justify-between font-light text-sm/[22px] bg-(--select) rounded-[20px] p-3 tracking-[-0.45px] select-none ${props.class}`"
                @click="onClick"
            >
                <span class="truncate">{{ title }}</span>

                <span
                    v-if="multiple && selected"
                    class="bg-(--button) rounded-full leading-[20px] w-[20px] h-[20px] text-center"
                >
                    {{ selected.length }}
                </span>

                <img
                    v-if="multiple && selected"
                    src="/images/cancel.svg"
                    width="22"
                    alt=""
                >
                <img
                    v-else
                    src="/images/down-arrow.svg"
                    width="22"
                    alt=""
                >
            </div>
        </template>

        <template v-slot:body="{onClick}">
            <slot />

            <button
                class="flex items-center justify-center gap-4 bg-(--button) rounded-full px-10 py-2.5 mx-auto my-5 text-[14px]/[22px]"
                @click="onClick"
            >
                <span class="font-semibold">Показать</span>
                <span class="flex gap-1 items-center font-light text-[12px]/[20px] tracking-[-0.45px]">
                    <img src="/images/items.svg" width="16" alt="">
                    <span>
                        <span class="font-medium">153&nbsp;</span>
                        <span class="font-light">Предложения</span>
                    </span>
                </span>
            </button>
        </template>
    </ModalPopup>
</template>

<style scoped>

</style>
