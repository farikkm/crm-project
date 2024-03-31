<script lang="ts" setup>
import { useAuthStore, useIsLoadingStore } from '~/store/auth.store';

// Stores
const isLoadingStore = useIsLoadingStore()
const authStore = useAuthStore()

// Router
const router = useRouter()

// onMounted
onMounted(async () => {
  try {
    isLoadingStore.set(true)
    const user = await account.get()
    if (user) authStore.set(user)
  } catch (error) {
    router.push('/login')
  } finally {
    isLoadingStore.set(false)
  }
})
</script>

<template>
  <LayoutLoader v-if="isLoadingStore.isLoading"/>
  <section v-else :class="{ grid: authStore.isAuth }" style="min-height: 100vh;">
    <LayoutSidebar v-if="authStore.isAuth"/>
    <div>
      <slot></slot>
    </div>
  </section>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: 1fr 6fr;
}
</style>