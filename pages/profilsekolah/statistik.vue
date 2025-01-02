<template>
    <div class="container mx-auto">

        <div class="grid grid-cols-2 gap-10 m-10">
            <v-card class="mx-auto text-center" min-width="500px" title="Jumlah Siswa">
                <v-card-subtitle>
                    <p class="text-[20px] font-semibold">{{ data.siswa }}</p>
                </v-card-subtitle>
            </v-card>
            <v-card class="mx-auto text-center" min-width="500px" title="Jumlah Rombel">
                <v-card-subtitle>
                    <p class="text-[20px] font-semibold">{{ data.rombel }}</p>
                </v-card-subtitle>
            </v-card>
            <v-card class="mx-auto text-center" min-width="500px" title="Jumlah Guru">
                <v-card-subtitle>
                    <p class="text-[20px] font-semibold">{{ data.guru }}</p>
                </v-card-subtitle>
            </v-card>
            <v-card class="mx-auto text-center" min-width="500px" title="Jumlah Tenaga Adinistrasi">
                <v-card-subtitle>
                    <p class="text-[20px] font-semibold">{{ data.administrasi }}</p>
                </v-card-subtitle>
            </v-card>
        </div>

        <div class="flex justify-center items-center gap-5">
            <div id="statistik" class="groupbar container mx-auto gap-20 items-center justify-center flex py-20">
                <v-card class="mx-auto text-center" title="Rekap Siswa Per Jurusan">
                    <div class="bar1 flex min-h-[300px] ">
                        <Bar class="p-5 min-w-[500px] max-w-[600px]" :options="jurusanChartOptions" :data="jurusanChartData" />
                    </div>
                </v-card>

                <v-card class="mx-auto text-center" title="Rekap Jenis Kelamin Siswa">
                    <div class="bar2 flex ">
                        <Pie class="p-5 max-h-[300px]" :options="kelaminChartOptions" :data="kelaminChartData" />
                    </div>
                </v-card>

                <v-card class="mx-auto text-center" title="Status Kepegawaian Guru">
                    <div class="bar2 flex" >
                        <Pie class="p-5 max-h-[300px]" :options="guruChartOptions" :data="guruChartData" />
                    </div>
                </v-card>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            data: {
                siswa: "1116",
                rombel: "34",
                guru: "60",
                administrasi: "10",
            }
        };
    }
};
</script>

<script setup>


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
                backgroundColor: ["darkblue", "magenta"],
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

<style scoped></style>