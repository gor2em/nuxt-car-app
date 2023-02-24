<script setup>
const route = useRoute();
useHead({
    title: `${route.params.make ? route.params.make : 'Cars'} in ${route.params.city}`,
})

definePageMeta({
    layout: "custom"
})
</script>

<template>
    <div>
        <div class="mt-32 flex">

            <NuxtErrorBoundary>

                <CarSideBar />
                <NuxtPage />

                <template #error="{ error }">
                    <div class="text-center mx-auto flex flex-col">
                        <h1 class="text-5xl font-bold mb-6 text-rose-600">Sorry, something went wrong</h1>
                        <code>{{ error }}</code>
                        <button @click="error.value = null" class="mt-8 font-bold bg-slate-200 px-4 py-2 rounded-lg">
                            Go Back
                        </button>
                    </div>
                </template>

            </NuxtErrorBoundary>

        </div>
    </div>
</template>