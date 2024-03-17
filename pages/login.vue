<script setup lang="ts">
useHead({
  title: 'Login | CRM System'
})

const emailRef = ref('')
const passwordRef = ref('')
const nameRef = ref('')

</script>

<template>
  <div class="flex justify-center items-center min-h-screen w-full">
    <div class="rounded bg-sidebar w-1/4 p-5">
      <h1 class="font-bold text-2xl text-center mb-5">Login</h1>

      <form>
        <UiInput v-model="emailRef" placeholder="Email" type="email" class="mb-3" />
        <UiInput v-model="passwordRef" placeholder="Password" type="password" class="mb-3" />
        <UiInput v-model="nameRef" placeholder="Name" type="name" class="mb-3" />

        <div class="flex items-center justify-center gap-5">
          <UiButton type="button">Login</UiButton>
          <UiButton type="button">Register</UiButton>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped></style>