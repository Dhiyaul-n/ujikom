<template>
    <div class="wrapper w-screen ">

        <div class="contain mx-0 w-[100vw]">
            <v-carousel height="500" class="relative h-[80vh] w-[100%]">
                <v-carousel-item class="rounded-lg w-" v-for="(item, i) in items" :key="i" :src="`/img/item/${item.src}`"
                    reverse-transition="fade-transition" transition="fade-transition"></v-carousel-item>
            </v-carousel>
        </div>

        <div class="container mx-auto">
            <div class="flex justify-center p-20 container mx-auto">
                <div class="grid grid-cols-2 max-w-[1200px]">
                    <div class="card flex justify-center">
                        <div class=" rounded-[1rem] hover:shadow-2xl duration-500 ease-in-out p-6 bg-[#efefef] mr-5">
                            <img src="../assets/img/kepala-sekolah.png" alt="Avatar" style="width:100%">
                            <div class="container">
                                <h2><b>KEPALA SEKOLAH</b></h2>
                                <p></p> Kurniawan s.pd m.pd
                            </div>
                        </div>
                    </div>
                    <div class="rounded-[1rem] hover:shadow-2xl duration-500 ease-in-out">
                        <p class="text-justify font-serif font-italic text-[16px] p-10">
                            Assalamu'alaikum warahmatullahi wabarakatuh, Salam sejahtera, Shalom, Om Swastiastu, Namo
                            Buddhaya Yang saya hormati, Para Wakil Kepala Sekolah, Guru, Staf, dan
                            Siswa.<br><br>Alhamdulillah, kita dapat berkumpul dalam acara ini berkat rahmat Allah SWT.
                            Terima kasih atas kehadiran semua pihak yang telah mendukung acara ini. Saya bangga dengan
                            kerja keras dan kontribusi semua pihak dalam mendukung kemajuan sekolah kita. Pendidikan
                            tidak hanya tentang ilmu, tetapi juga tentang pembentukan karakter. Untuk itu, mari kita
                            terus bekerja sama agar sekolah ini terus maju dan memberikan pendidikan terbaik untuk masa
                            depan yang gemilang. Semoga kita selalu diberikan kesehatan dan kekuatan untuk terus
                            berusaha memberikan yang terbaik. Terima kasih atas perhatian dan kerjasamanya.
                            Wassalamu'alaikum warahmatullahi wabarakatuh. Semoga rangkuman ini sesuai dengan yang Anda
                            harapkan!
                        </p>
                    </div>
                </div>
            </div>

            <NuxtLink to="galery">
                <h1 class="text-[50px] text-center font-playfair font-medium mt-10">Galeri
                </h1>
            </NuxtLink>

            <div class="flex justify-center mt-5 mb-10">
                <v-sheet v-for="(galery, i) in galery" :key="i"
                    class="flex bg-[#eee] hover:shadow-2xl ease-in-out px-10 rounded-xl grayscale hover:grayscale-0 duration-700 scale-95 hover:scale-105 "
                    :height="500" :width="500" rounded>
                    <img class="rounded-2xl blur-sm hover:blur-0 duration-700" :src="`/img/galery/${galery.src}`">
                    <div class="text text-center text-[30px] font-playfair ">
                        <h1>{{ galery.name }}</h1>
                    </div>
                </v-sheet>
            </div>

            <NuxtLink to="../profilsekolah/statistik">
                <h1 class="text-[50px] text-center font-playfair font-medium mt-10">Statistik
                </h1>
            </NuxtLink>

            <div id="statistik" class="groupbar container mx-auto gap-20 items-center justify-center flex py-20">
                <div class="bar1 flex w-[500px] ">
                    <Bar :options="jurusanChartOptions" :data="jurusanChartData" />
                </div>
                <div class="bar2 flex w-[300px] ">
                    <Pie :options="kelaminChartOptions" :data="kelaminChartData" />
                </div>
                <div class="bar2 flex w-[300px] ">
                    <Pie :options="guruChartOptions" :data="guruChartData" />
                </div>
            </div>

            <div class="flex justify-center">
                <iframe class="max-w-[1000px] p-20"
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3957.213116362029!2d108.25189907500041!3d-7.329945292678408!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e6f59eeb6bda36f%3A0xa9e724a275da6c2d!2sSMK%20Negeri%204%20Tasikmalaya!5e0!3m2!1sid!2sid!4v1735548496522!5m2!1sid!2sid"
                    width="100%" height="500px" style="" allowfullscreen="" loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>

        </div>
    </div>
</template>

<style scoped>

    .wrapper {
        background: white;
    }
    
.contain {
    background: linear-gradient(180deg, #011a3b, #033d8c);
}
</style>


<script setup>


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

])

const items = ref([
    {
        src: 'homeimg.jpg',
    },
    {
        src: 'carousel.jpeg',
    },
    {
        src: 'profil.jpg',
    },
])


import {
    Bar,
    Pie
} from "vue-chartjs"

const jurusanChartData = computed(() => {
    return {
        labels: ["DKV", "PPLG", "TJKT", "TOI", "TBSM"],
        datasets: [
            {
                label: "Jumlah Siswa per Jurusan",
                backgroundColor: ["#e05739", "#007840", "#000ac5", "#d0d0d0", "#e00000"],
                data: [196, 352, 374, 96, 369],
            },
        ],
    }
});

const jurusanChartOptions = ref({
    title: {
        display: true,
        text: "Line Chart Products",
    },
    scales: {
        yAxes: [
            {
                ticks: {
                    beginAtZero: true,
                },
            },
        ],
    }
})

const kelaminChartData = computed(() => {
    return {
        labels: ["Laki-Laki", "Perempuan"],
        datasets: [
            {
                label: "Rekap jenis Kelamin Siswa",
                backgroundColor: ["blue", "pink"],
                data: [196, 369],
            },
        ],
    }
});

const ChartOptions = ref({
    title: {
        display: true,
        text: "Line Chart Products",
    },
    scales: {
        yAxes: [
            {
                ticks: {
                    beginAtZero: true,
                },
            },
        ],
    }
})

const guruChartData = computed(() => {
    return {
        labels: ["PNS", "non PNS"],
        datasets: [
            {
                label: "Status Kepegawaian Pendidik",
                backgroundColor: ["red", "green"],
                data: [22, 32],
            },
        ],
    }
});

const kguruChartOptions = ref({
    title: {
        display: true,
        text: "Line Chart Products",
    },
    scales: {
        yAxes: [
            {
                ticks: {
                    beginAtZero: true,
                },
            },
        ],
    }
})

</script>
