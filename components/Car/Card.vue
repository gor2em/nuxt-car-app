<script setup>

import heartFilled from "@/assets/heartFilled.png";
import heartOutline from "@/assets/heartOutline.png";

const props = defineProps({
    car: Object,
    favored: Boolean,
});

//unique
// const favored = useState(`favored-${props.car.id}`, () => {
//     return false
// })

const emit = defineEmits(['favor'])
</script>

<template>
    <div class="relative shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px]">
        <img :src="favored ? heartFilled : heartOutline" class="absolute w-7 right-5 top-2 z-20"
            @click="emit('favor', car.id)">
        <div class="flex h-full" @click="navigateTo(`/car/${car.name}-${car.id}`)">
            <NuxtImg :src="car.url" class="w-[300px] h-full" alt="" />
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