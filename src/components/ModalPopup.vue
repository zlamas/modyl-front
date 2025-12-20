<script setup>
import {ref, useTemplateRef, watch} from "vue";

const props = defineProps({
    title: String,
    icon: String,
});

const open = defineModel('open', {default: false});

watch(
    () => open.value,
    (open) => {
        if (open) {
            dragAmount.value = 0;
            dragSpeed = 0;
        }
    }
);

const container = useTemplateRef('container');
const header = useTemplateRef('header');

const dragging = ref(false);
const dragAmount = ref(0);
let dragSpeed = 0;
let startY = 0;
let previousY = 0;

function onPointerDown(event) {
    if (header.value.contains(event.target)) {
        dragging.value = true;
        startY = previousY = event.clientY;
    }
}

function onPointerMove(event) {
    if (dragging.value) {
        dragSpeed = event.clientY - previousY;
        previousY = event.clientY;
        dragAmount.value =
            Math.max(event.clientY - startY, 0) / container.value.offsetHeight;
    }
}

function onPointerUp() {
    if (dragAmount.value > 0.5 || dragSpeed > 20) {
        open.value = false;
    } else {
        dragAmount.value = 0;
    }
    dragging.value = false;
}
</script>

<template>
    <slot :onClick="() => open = true" />

    <Teleport to="body">
        <Transition name="fade">
            <div
                v-show="open"
                :class="[
                    'modal-overlay fixed inset-0 bg-black/70 touch-none',
                     { dragging }
                ]"
                @click="open = false"
            ></div>
        </Transition>
        <Transition name="slide-up">
            <div
                ref="container"
                v-show="open"
                :class="[
                    'modal-container flex flex-col bg-white fixed max-h-full inset-0 top-auto rounded-t-[25px] touch-none',
                    { dragging }
                ]"
                v-on="{
                    pointerdown: onPointerDown,
                    pointermove: onPointerMove,
                    pointerup: onPointerUp,
                }"
            >
                <div
                    ref="header"
                    class="flex items-center px-6 py-2.5 border border-(--border)/25 touch-auto"
                >
                    <div
                        v-if="title || icon"
                        class="flex items-center gap-2.5 text-[20px]/1 font-bold tracking-[-0.45px]"
                    >
                        <img v-if="icon" :src="`images/${icon}.svg`" alt="">
                        <span v-if="title">{{ title }}</span>
                    </div>
                    <slot v-else name="header" />

                    <button class="bg-(--card)/20 rounded-full px-[15px] py-[9px] ml-auto" @click.stop="open = false">
                        <img src="/images/cancel.svg" width="22" alt="">
                    </button>
                </div>

                <div class="overflow-auto">
                    <slot name="body" :onClick="() => open = false" />
                </div>
            </div>
        </Transition>
    </Teleport>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.3s;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.slide-up-enter-active,
.slide-up-leave-active {
    transition: translate 0.3s;
}

.slide-up-enter-from,
.slide-up-leave-to {
    translate: 0 100%;
}

.modal-overlay {
    &.dragging {
        opacity: v-bind('`${1 - dragAmount}`');
    }

    &:not(.dragging) {
        transition-duration: 0.3s;
    }
}

.modal-container {
    &.dragging {
        translate: 0 v-bind('`${dragAmount * 100}%`');
    }

    &:not(.dragging) {
        transition-duration: 0.3s;
    }
}
</style>
