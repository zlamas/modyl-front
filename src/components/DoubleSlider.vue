<script setup>
import {computed, ref, useTemplateRef} from "vue";

const value = defineModel('value', {default: [0, 100]});

const style = computed(() => value.value.map(
    (value) => ({
        left: `${value}%`,
        translate: `-${value}% 0`
    })
));

const slider = useTemplateRef('slider');

const sliderDragTarget = ref(null);

function onPointerDown(target) {
    sliderDragTarget.value = target;
}

function onPointerMove(event) {
    if (sliderDragTarget.value) {
        const position = (event.pageX - slider.value.offsetLeft) / slider.value.offsetWidth * 100;

        let [min, max] = value.value;

        if (sliderDragTarget.value === 'left') {
            min = Math.max(0, Math.min(position, max));
        } else if (sliderDragTarget.value === 'right') {
            max = Math.max(min, Math.min(position, 100));
        }

        value.value = [min, max];
    }
}

function onPointerUp() {
    sliderDragTarget.value = null;
}
</script>

<template>
    <div
        ref="slider"
        class="relative bg-[#F3F2F2] rounded-full h-[5px]"
        @pointermove="onPointerMove"
        @pointerup="onPointerUp"
    >
        <span
            class="absolute w-[20px] h-[20px] bg-(--border) rounded-full inset-y-0 my-auto"
            :style="style[0]"
            @pointerdown="() => onPointerDown('left')"
        ></span>
        <span
            class="absolute w-[20px] h-[20px] bg-(--border) rounded-full inset-y-0 my-auto"
            :style="style[1]"
            @pointerdown="() => onPointerDown('right')"
        ></span>
    </div>
</template>

<style scoped>

</style>
