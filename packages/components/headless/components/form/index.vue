<template>
  <Form :validation-schema="validationSchema" @submit="onSubmit">
    <Field name="email" type="email" />
    <ErrorMessage name="email" />
    <Field name="password" type="password" />
    <ErrorMessage name="password" />
    <button>Submit</button>
  </Form>
</template>

<script setup>
import { ErrorMessage, Field, Form } from 'vee-validate'
import { toTypedSchema } from '@vee-validate/zod'
import * as zood from 'zod'

const validationSchema = toTypedSchema(
  zood.object({
    email: zood
      .string()
      .min(1, { message: 'This is required' })
      .email({ message: 'Must be a valid email' }),
    password: zood
      .string()
      .min(1, { message: 'This is required' })
      .min(8, { message: 'Too short' }),
  })
)
function onSubmit(values) {
  alert(JSON.stringify(values, null, 2))
}
</script>
