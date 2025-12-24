<script setup>
import HeaderBlock from "./HeaderBlock.vue";

const props = defineProps({
    class: {
        type: String,
        default: ''
    }
})
</script>

<template>
    <HeaderBlock>
        <slot name="header" />
    </HeaderBlock>

    <main :class="`p-5 pt-2.5 ${props.class}`">
        <slot />
    </main>
</template>

<style scoped>

</style>
