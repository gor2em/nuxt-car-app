<script setup>
const props = defineProps({
    car: Object
});
</script>

<template>
    <div class="shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px]"
    @click="navigateTo(`/car/${car.name}-${car.id}`)"
    >
        <div class="flex h-full">
            <img :src="car.url"
                class="w-[300px] h-full" alt="">
            <div class="p-4 flex flex-col">
                <div>
                    <h1 class="text-2xl text-blue-700">
                        {{ car.name }}
                    </h1>
                    <p class="text-gray-700">{{ car.description }}</p>
                </div>
                <h3 class="text-xl mt-auto">{{ car.price }}</h3>
            </div>
        </div>
    </div>
</template>