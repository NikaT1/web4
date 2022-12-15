<template>
  <input type="text" :name="name" maxlength="17" autocomplete="off"
         :placeholder="placeholder" :value="param"
         @input="$emit('update:param', $event.target.value)">
</template>

<script>
export default {
  name: "InputWithCheck",
  props: ['name', 'placeholder', 'param'],
  emits: ['update:param'],
}
</script>

<style scoped>

</style>