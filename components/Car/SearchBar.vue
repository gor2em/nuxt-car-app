<script setup>
const city = ref("");
const cityError = ref("");
// const router = useRouter();

const handleSearch = () => {
    // router.push(`/city/${city.value}/car`)
    if (!city.value) {
        return cityError.value = true;
    }

    navigateTo(`/city/${city.value}/car`)

}
</script>

<template>
    <div class="w-full text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto">
        <input type="text" :class="cityError ? 'border border-red-600' : ''" class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none" placeholder="search by city..."
            v-model="city" />

        <button class="bg-pink-400 px-4 text-white font-bold" @click="handleSearch">search</button>
    </div>
</template>