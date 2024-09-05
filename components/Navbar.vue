<template>
    <nav :class="isFloat ? 'fixed bg-eb-white shadow-lg' : 'absolute bg-transparent'" class="px-4 lg:px-36 w-full h-20 grid grid-cols-4 transition-all duration-300 items-center gap-0 z-[99]">
        <div class="col-span-1 flex items-center justify-start gap-x-6">
            <nuxt-link to="/">
                <img preload src="/img/logo_ebond.png" alt="logo ebond" width="56" height="56" loading="eager" title="logo ebond" class="object-cover object-center h-16"/>
            </nuxt-link>
        </div>
        <div class="col-span-2">
            <div class="hidden lg:flex justify-evenly">
                <NuxtLink to="/" activeClass="bg-eb-white4 rounded-2xl shadow font-bold">
                    <button class="text-center font-anek flex items-center gap-x-1 rounded-xl cursor-pointer transition-all duration-300 p-4 ease-in-out border-none outline-none leading-none hover:shadow hover:ring hover:ring-eb-green5 hover:text-eb-green2">
                        Halaman Utama
                    </button>
                </NuxtLink>
                <NuxtLink to="/colors" activeClass="bg-eb-white4 rounded-2xl shadow font-bold">
                    <button class="text-center font-anek flex items-center gap-x-1 rounded-xl cursor-pointer transition-all duration-300 p-4 ease-in-out border-none outline-none leading-none hover:shadow hover:ring hover:ring-eb-green5 hover:text-eb-green2">
                        Color Chart
                    </button>
                </NuxtLink>
                <NuxtLink to="/installation" activeClass="bg-eb-white4 rounded-2xl shadow font-bold">
                    <button class="text-center font-anek flex items-center gap-x-1 rounded-xl cursor-pointer transition-all duration-300 p-4 ease-in-out border-none outline-none leading-none hover:shadow hover:ring hover:ring-eb-green5 hover:text-eb-green2">
                        Pemasangan ACP
                    </button>
                </NuxtLink>
            </div>
            
        </div>
        <div class="col-span-1 flex w-full justify-end">
            <NuxtLink to="/contact">
                <ButtonBase class="hidden lg:block main">
                    Kontak Kami
                </ButtonBase>
            </NuxtLink>
            <ButtonBase @click="switchOpen()" :class="isOpen ? 'danger' : 'main' " class="lg:hidden">
                {{ isOpen ? 'Close' : 'Menu' }}
            </ButtonBase>
        </div>
        <div v-if="isOpen" class="col-span-4 relative z-50">
            <div class="absolute w-full flex justify-end ">
                <div class="bg-eb-white4 shadow-lg p-4 rounded-2xl mt-4 min-w-44">
                    <div class="border-l-4 pl-3 mb-3 border-eb-green5">
                        <p class="text-xl font-semibold">
                            Menu
                        </p>
                    </div>
                    <div class="flex flex-col justify-evenly">
                        <NuxtLink to="/" activeClass="bg-eb-white rounded-r-2xl font-bold">
                            <button @click="switchOpen()" class="text-center font-anek flex items-center gap-x-1 rounded-xl cursor-pointer transition-all duration-300 py-4 px-6 ease-in-out border-none outline-none leading-none hover:shadow hover:ring hover:ring-eb-green5 hover:text-eb-green2">
                                Home
                            </button>
                        </NuxtLink>
                        <NuxtLink to="/colors" activeClass="bg-eb-white rounded-r-2xl font-bold">
                            <button @click="switchOpen()" class="text-center font-anek flex items-center gap-x-1 rounded-xl cursor-pointer transition-all duration-300 py-4 px-6 ease-in-out border-none outline-none leading-none hover:shadow hover:ring hover:ring-eb-green5 hover:text-eb-green2">
                                Color Chart
                            </button>
                        </NuxtLink>
                        <NuxtLink to="/installation" activeClass="bg-eb-white rounded-r-2xl font-bold">
                            <button @click="switchOpen()" class="text-center font-anek flex items-center gap-x-1 rounded-xl cursor-pointer transition-all duration-300 py-4 px-6 ease-in-out border-none outline-none leading-none hover:shadow hover:ring hover:ring-eb-green5 hover:text-eb-green2">
                                Pemasangan
                            </button>
                        </NuxtLink>
                        <NuxtLink to="/contact" activeClass="bg-eb-white rounded-r-2xl font-bold">
                            <button @click="switchOpen()" class="text-center font-anek flex items-center gap-x-1 rounded-xl cursor-pointer transition-all duration-300 py-4 px-6 ease-in-out border-none outline-none leading-none hover:shadow hover:ring hover:ring-eb-green5 hover:text-eb-green2">
                                Kontak Kami
                            </button>
                        </NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script lang="ts" setup>
const isOpen = ref(false)
const isFloat = ref(false)

onMounted(() => {
    document.addEventListener('scroll', function() {
        let bodyTopPosition = document.body.getBoundingClientRect().top;

        if( bodyTopPosition < -50 ){
            isFloat.value = true
        } else {
            isFloat.value = false
        }
    })
})

const switchOpen = () => {
    isOpen.value = !isOpen.value
}


</script>

<style scoped>
.slide-enter-active,
.slide-leave-active {
    transition: all 0.5s ease-in-out;
}


.slide-enter-from,
.slide-leave-to {
    transform: translateX(100vh);
}
</style>