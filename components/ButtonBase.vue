<template>
    <button class="text-center font-anek flex items-center gap-x-1 font-semibold rounded-xl shadow cursor-pointer transition-all duration-300 py-4 px-6 ease-in-out border-none outline-none leading-none">
        <slot />
    </button>
</template>

<script setup lang="ts">

</script>

<style lang="postcss" scoped>
.main {
    @apply bg-eb-green5 text-eb-white hover:bg-eb-green4 hover:text-eb-white3
}
.warning {
    @apply bg-eb-yellow text-eb-black hover:bg-eb-yellow2 hover:text-eb-white3
}
.danger {
    @apply bg-eb-red text-eb-white3 hover:bg-eb-red2
}
.dark {
    @apply text-eb-white bg-eb-dark hover:bg-eb-black
}

.inverted {
    @apply font-semibold text-eb-blue2 ring ring-eb-primary hover:ring-eb-dark hover:text-eb-white hover:bg-eb-dark
}
.outline {
    @apply hover:ring hover:ring-eb-primary 
}
.outline-dark {
    @apply hover:ring hover:ring-eb-white
}
.none {
    @apply shadow-none hover:bg-eb-white4
}
.none {
    @apply shadow-none hover:bg-eb-white4 hover:shadow
}
</style>