<template>
  <div>
    <h1>{{ greet }}<button @click="$emit('close')">x</button></h1>
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
</script>
