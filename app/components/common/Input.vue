<template>
  <div class="flex flex-col gap-1 w-full">
    <label v-if="label" class="text-sm font-medium text-gray-700">
      {{ label }}
    </label>

    <div
      class="flex items-center border rounded-md px-3 py-2 bg-white"
      :class="[
        disabled ? 'bg-gray-100 cursor-not-allowed' : 'focus-within:border-blue-500',
        error ? 'border-red-500' : 'border-gray-300'
      ]"
    >
      <!-- Start Icon slot -->
      <slot name="startIcon"></slot>

      <input
        class="flex-1 outline-none text-sm bg-transparent"
        :type="type"
        :placeholder="placeholder"
        :disabled="disabled"
        :value="text"
        @input="$emit('update:text', ($event.target as HTMLInputElement).value)"
      />

      <!-- End Icon slot -->
      <slot name="endIcon"></slot>
    </div>

    <!-- Validation / Error -->
    <p v-if="error" class="text-xs text-red-500 mt-1">{{ error }}</p>
  </div>
</template>

<script setup lang="ts">
interface Props {
  text: string | number | null;
  label?: string;
  placeholder?: string;
  type?: string;
  disabled?: boolean;
  error?: string;
}

withDefaults(defineProps<Props>(), {
  type: "text",
  disabled: false,
});
defineEmits(["update:text"]);
</script>

<style scoped>
/* optional custom styles */
</style>
