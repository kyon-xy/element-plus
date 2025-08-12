<template>
  <Field v-bind="$attrs">
    <template #default="fieldBindings">
      <slot :field-bindings="fieldBindings" />
    </template>
  </Field>
</template>

<script setup lang="ts">
import { Field } from 'vee-validate'
</script>
