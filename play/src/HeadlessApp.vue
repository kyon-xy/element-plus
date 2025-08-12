<template>
  <!-- If you want to apply a custom namespace, uncomment the following and apply the css configuration in `vite.config.ts`. -->
  <!-- <el-config-provider namespace="ep"> -->
  <div class="play-container">
    <!-- <Form>
      <Field name="email" type="email" :rules="fieldSchema" />
      <ErrorMessage name="email" />
    </Form> -->
    <HeadlessForm>
      <HeadlessFormItem name="email" type="email" :rules="fieldSchema" />
    </HeadlessForm>
  </div>
  <!-- </el-config-provider> -->
</template>

<script setup lang="ts">
import { Field, Form, ErrorMessage } from 'vee-validate'
import { toTypedSchema } from '@vee-validate/zod'
import * as zood from 'zod'
import { HeadlessForm, HeadlessFormItem } from '@shana/headless-form'
const fieldSchema = toTypedSchema(
  zood.string().nonempty('Field is required').email('Must be a valid email')
)
</script>

<style lang="scss">
html,
body {
  width: 100vw;
  height: 100vh;
  margin: 0;

  #play {
    height: 100%;
    width: 100%;

    .play-container {
      height: 100%;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
}
</style>
