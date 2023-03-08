
<template>

    <div class="w-full h-full flex gap-5 justify-center items-center text-white font-space">
        <div class="w-fit h-fit flex flex-row gap-10">
            <h1 class="text-9xl mb-4 underline "> Is it <br> Possible? </h1>
            <div>
                <ul class="text-3xl list-outside list-disc mx-8">
                    <li :style="{ opacity: step < 1 ? '0' : '1' }">Theorethically</li>
                    <li :style="{ opacity: step < 2 ? '0' : '1' }">Alcubierre Drive</li>
                    <li :style="{ opacity: step < 3 ? '0' : '1' }">FTL achieved by bendng spacetime</li>
                    <li :style="{ opacity: step < 4 ? '0' : '1' }">Works with Einstein's equations</li>
                    <li :style="{ opacity: step < 5 ? '0' : '1' }">Implies negative energy density =&gt; requires exotic matter</li>
                    <li :style="{ opacity: step < 6 ? '0' : '1' }">Really Cool</li>
                </ul>
            </div>
        </div>
    </div>

</template>

<script setup lang="ts">

import { onKeyUp } from '@vueuse/core';
import { onMounted, ref } from 'vue';
const step = ref(0);

onMounted(() => {
    onKeyUp(" ", () => {
        step.value++
    });
})
</script>