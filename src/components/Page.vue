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

    <main :class="`px-5 py-2.5 ${props.class}`">
        <slot />
    </main>
</template>

<style scoped>

</style>
