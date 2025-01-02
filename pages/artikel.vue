<template>
    <div class="container mx-auto">
        <div class="grid grid-cols-2 gap-y-5 gap-x-10 my-10">
            <v-sheet v-for="(artikel, i) in artikel" :key="i" class="bg-[#eee] m-5 hover:shadow-2xl ease-in-out duration-700 px-10 w-[100%] flex" :height="200" rounded>
                <img class="h-[100px]" :src="`/img/news/${artikel.src}`">
                <div class="">
                    <a href="" class="text-[20px] font-sans text-blue-500">{{ artikel.name }}</a>
                    <p class="date">{{ artikel.date }}</p>
                    <p class="penerbit">{{ artikel.penulis }}</p>
                </div>
            </v-sheet>
        </div>
    </div>
</template>

<script setup>

const artikel = ref([
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },

    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },
    {
        name: "Pengumuman Ujikom",
        date:"02-02-2025",
        penulis:"SMKN 4 TASIKMALAYA",
        src: 'news.1.jpg',
    },

])
</script>

<style lang="scss" scoped>

</style>