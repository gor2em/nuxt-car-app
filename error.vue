<script setup>
const error = useError();
</script>

<template>
    <div class="flex flex-col min-h-screen justify-center items-center">
        <h1 class="md:text-9xl font-bold ">{{ error.statusCode }}</h1>
        <p class="text-sm">
            {{ error.message }}
        </p>
        <nuxt-link to="/" class="mt-8 font-bold bg-slate-200 px-4 py-2 rounded-lg">
            Go Back
        </nuxt-link>
    </div>
</template>