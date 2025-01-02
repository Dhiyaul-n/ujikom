<template>
    <div class="container mx-auto my-20">
        <div class="grid grid-cols-3 gap-10">
            <v-sheet v-for="(galery, i) in galery" :key="i" class="flex bg-[#eee] hover:shadow-2xl ease-in-out px-10 rounded-xl grayscale hover:grayscale-0 duration-700 scale-75 hover:scale-105 " :height="500" :width="500" rounded>
                <img class="rounded-2xl blur-sm hover:blur-0 duration-700" :src="`/img/galery/${galery.src}`">
                <div class="text text-center text-[30px] font-playfair ">
                    <h1>{{ galery.name }}</h1>
                </div>
            </v-sheet>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const galery = ref([
    { 
        name: "MPLS 2024",
        src: 'galery.jpg',
    },

    { 
        name: "Hari Guru 2024",
        src: 'galery1.jpg',
    },

    { 
        name: "Classmeet 2024",
        src: 'galery2.jpg',
    },

    { 
        name: "Upacara Kemerdekaan 2024",
        src: 'galery3.jpg',
    },

        { 
        name: "P5 Melamar Kerja",
        src: 'galery4.jpg',
    },
])
</script>

<style lang="scss" scoped>

</style>