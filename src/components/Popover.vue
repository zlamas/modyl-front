<script setup>
import {onMounted, ref, useTemplateRef, watch} from "vue";

const props = defineProps({
    icon: String,
    items: Array,
    offset: {
        type: Number,
        default: 10
    },
});

const button = useTemplateRef('button');
const popover = useTemplateRef('popover');

const open = ref(false);

const selected = ref(0);

onMounted(() => {
    document.addEventListener('click', (event) => {
        if (!popover.value?.contains(event.target)) {
            open.value = false;
        }
    });
});

watch(
    open,
    (open) => {
        if (!open) return;

        const buttonRect = button.value.getBoundingClientRect();

        Object.assign(popover.value.style, {
            top: `${window.scrollY + buttonRect.bottom + props.offset}px`,
            right: `${window.innerWidth - buttonRect.right}px`,
        });
    }
);

function selectItem(index) {
    selected.value = index;
    open.value = false;
}
</script>

<template>
    <button
        ref="button"
        class="shrink-0"
        @click.stop="open = !open"
    >
        <img :src="icon" width="24" alt="">
    </button>

    <div
        v-show="open"
        ref="popover"
        class="absolute grid gap-2 bg-white rounded-[10px] text-[14px]/[22px] overflow-hidden shadow-[0_9px_28px_8px_#0000000D]"
    >
        <div
            v-for="(item, index) in items"
            :key="index"
            :class="['px-4 py-2', {
                'bg-[#C9D2D14D] font-semibold': index === selected,
            }]"
            @click="selectItem(index)"
        >
            {{ item }}
        </div>
    </div>
</template>

<style scoped>

</style>
