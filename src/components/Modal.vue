<template>
  <teleport to=".modals-container">
  <div
    v-if="modelValue"
    class="modal"
  >
    <h1>{{ title }}</h1>
    <slot />
    <button @click="$emit('hideModal')">Hide modal</button>
  </div>
</teleport>
</template>

<script setup>
  const props = defineProps({
    modelValue: {
      type: Boolean,
      default: false
    },
    title: {
      type: String,
      default:'no title specified'
    }
  })

  const emit = defineEmits(['hideModal'])

</script>

<style>
  .modal {
    background: beige;
    color: black;
    padding: 10px;
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
  }
</style>