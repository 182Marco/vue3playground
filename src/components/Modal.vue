<template>
  <div>
    <h1>{{ greet }}<button @click="$emit('close', 3)">x</button></h1>
    <slot></slot>
    <slot name="namedSlot"></slot>
  </div>
</template>

<script setup>
const props = defineProps({
  greet: {
    type: String,
    default: 'default value'
  }
})
const emit = defineEmits([])
</script>
