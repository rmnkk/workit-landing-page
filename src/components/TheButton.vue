<script setup lang="ts">
export interface ButtonProps {
    buttonVariant: 'primary' | 'secondary';
}

withDefaults(defineProps<ButtonProps>(), {
    buttonVariant: 'primary',
});
</script>

<template>
    <button type="button" class="button" :class="`button-${buttonVariant}`">
        <slot />
    </button>
</template>

<style scoped>
.button {
    font-weight: 700;
    font-size: var(--font-size-regular);
    line-height: 2rem;
    letter-spacing: -0.011rem;
    cursor: pointer;
    transition: all 0.25s linear;
}

.button-primary {
    padding: 0.8rem 1.4rem;
    background-color: var(--color-secondary);
    border: 0.125rem solid transparent;
    color: var(--color-primary);
}

.button-primary:hover {
    background-color: var(--color-primary);
    border-color: var(--color-secondary);
    color: var(--color-secondary);
}

.button-secondary {
    padding: 0;
    background-color: transparent;
    color: #fff;
    border: none;
    border-bottom: 0.125rem solid var(--color-secondary);
}

.button-secondary:hover {
    color: var(--color-secondary);
}
</style>