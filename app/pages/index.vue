<template>
<div>
    <h1>Welcome to the Home Page</h1>
    <li v-for="(item, index) in res" :key="index">{{ item }}</li>   
    <Input v-model:text="text" label="label of Item" placeholder="Item">
        <template #startIcon>X</template>
        <template #endIcon>X</template>
        </Input>
    {{ text }}
    <Header label="My Header">
        <p>This is some content inside the header component.</p>
    </Header>
</div>
</template>
<script setup>
import Input from '@/components/common/Input.vue';
import Header from '@/components/ui/Header.vue';
import { ref } from 'vue';
const text = ref('');
const res = ref(['apple', 'banana', 'cherry']);


</script>