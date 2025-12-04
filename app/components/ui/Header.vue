<template>
    <div>
        <label> {{ label }}</label>
        <header>
            <slot></slot>
        </header>
    </div>
</template>
<script setup lang="ts">
interface Props {
    label: string;
    }

withDefaults(defineProps<Props>(), {
    label: 'Header',
});


</script>