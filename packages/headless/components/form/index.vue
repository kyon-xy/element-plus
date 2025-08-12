<template>
  <Form v-bind="$attrs">
    <template #default="formBindings">
      <slot :form-bindings="formBindings" />
    </template>
  </Form>
</template>

<script setup lang="ts">
import { Form } from 'vee-validate'
</script>
