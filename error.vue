<script setup>
const error = useError();
const handleError = () => {
    clearError({
        redirect: "/"
    });
}
</script>

<template>
    <div class="flex flex-col min-h-screen justify-center items-center">
        <h1 class="md:text-9xl font-bold ">{{ error.statusCode }}</h1>
        <p class="text-sm">
            {{ error.message }}
        </p>
        <button @click="handleError" class="mt-8 font-bold bg-slate-200 px-4 py-2 rounded-lg">
            Go Back
        </button>
    </div>
</template>