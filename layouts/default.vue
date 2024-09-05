<template>
    <div class="relative flex flex-col w-full min-h-screen bg-eb-white text-eb-black3 overflow-hidden scroll-smooth ">
        <Navbar />
        <div class="relative w-full">
            <slot />
        </div>
        <Footer />
    </div>
</template>

<script setup lang="ts">

</script>
