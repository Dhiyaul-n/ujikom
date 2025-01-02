<template>
    <div class="container h-[100vh] mx-auto">
        <div class="grid grid-cols-5 gap-y-5  gap-x-10">
            <v-sheet v-for="(jurusan, i) in jurusan" :key="i" class="flex bg-[#eee] mt-15 hover:shadow-2xl ease-in-out duration-700 p-5 px-10 rounded-xl border-t-6 border-[#ffad00]" :height="300" :width="300" rounded>
                <img class="rounded-2xl w-[100%] h-[80%]" :src="jurusan.src">
                <div class="text text-center text-[20px] font-playfair ">
                    <h1>{{ jurusan.name }}</h1>
                </div>
            </v-sheet>

        </div>
    </div>
</template>

<script setup>

import DKV from "../assets/img/jurusan/DKV.jpg"
import RPL from "../assets/img/jurusan/RPL.jpg"
import TKJ from "../assets/img/jurusan/TKJ.jpg"
import TOI from "../assets/img/jurusan/TOI.jpg"
import TSM from "../assets/img/jurusan/TSM.jpg"

const jurusan = ref([
    { src: DKV, name: "Desain Komunikasi Visual"},
    { src: RPL, name: "Pengembangan Perangkat Lunak dan GIM"},
    { src: TKJ, name: "Teknik Jaringan dan Komputer"},
    { src: TOI, name: "Teknik Otomasi Industri"},
    { src: TSM, name: "Teknik Bisnis Sepeda Motor"},
])

</script>

<style lang="scss" scoped>

</style>