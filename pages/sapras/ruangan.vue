<template>
    <div class="container mx-auto my-20">
        <div class="flex justify-center flex-wrap gap-8">
            <v-card @click="toggleShow(kelas)" v-for="(kelas, i) in kelas" class="flex w-[450px]">
                <v-img class="text-center align-text-bottom text-gray w-full h-full"
                    :src="`/img/ruangkelas/${kelas.src}`" aspect-ratio="2" cover>
                    <v-card-title class="text-white bg-black/40 bg-opacity-50">{{ kelas.name }}</v-card-title>
                </v-img>
                <v-dialog class="text-center ease-in-out duration-700 " v-model="dialog" width="auto">
                    <v-card min-width="400">
                        <v-img class="align-end text-white" width="1000" :src="`/img/ruangkelas/${selectedKelas.src}`">
                            <v-card-title> {{ selectedKelas.name }}</v-card-title>
                        </v-img>
                        <template v-slot:actions>
                            <v-btn class="ms-auto" text="Close" @click="dialog = false"></v-btn>
                        </template>
                    </v-card>
                </v-dialog>
            </v-card>
        </div>
    </div>
</template>

<script setup>

const dialog = ref(false)

const toggleShow = (kelas) => {
    selectedKelas.value = kelas;
    dialog.value = true
}

const selectedKelas = ref({})

const kelas = ref([
    {
        id: 1,
        src: 'main(1).jpg',
        name: 'Ruang 1'
    },
    {
        id: 2,
        src: 'main(2).jpg',
        name: 'Ruang 2'
    },

    {
        id: 3,
        src: 'main(3).jpg',
        name: 'Ruang 3'
    },

    {
        id: 4,
        src: 'main(4).jpg',
        name: 'Ruang 4'
    },

    {
        id: 5,
        src: 'main(5).jpg',
        name: 'Ruang 5'
    },

    {
        id: 6,
        src: 'main(6).jpg',
        name: 'Ruang 6'
    },

    {
        id: 7,
        src: 'main(7).jpg',
        name: 'Ruang 7'
    },

    {
        id: 8,
        src: 'main(8).jpg',
        name: 'Ruang 8'
    },
    {
        id: 9,
        src: 'main(9).jpg',
        name: 'Ruang 9'
    },
    {
        id: 10,
        src: 'main(10).jpg',
        name: 'Ruang 10'
    },
    {
        id: 11,
        src: 'main(11).jpg',
        name: 'Ruang 11'
    },
    {
        id: 12,
        src: 'main(12).jpg',
        name: 'Ruang 12'
    },
    {
        id: 13,
        src: 'main(13).jpg',
        name: 'Ruang 13'
    },
    {
        id: 14,
        src: 'main(14).jpg',
        name: 'Ruang 14'
    },
    {
        id: 15,
        src: 'main(15).jpg',
        name: 'Ruang 15'
    },
    {
        id: 16,
        src: 'main(16).jpg',
        name: 'Ruang 16'
    },
    {
        id: 17,
        src: 'main(17).jpg',
        name: 'Ruang 17'
    },
    {
        id: 18,
        src: 'main(18).jpg',
        name: 'Ruang 18'
    },
    {
        id: 19,
        src: 'main(19).jpg',
        name: 'Ruang 19 (Bengkel TBSM)'
    },
    {
        id: 20,
        src: 'main(20).jpg',
        name: 'Ruang 20'
    },
    {
        id: 21,
        src: 'main(21).jpg',
        name: 'Ruang 21'
    },
    {
        id: 22,
        src: 'main(22).jpg',
        name: 'Ruang 22'
    },
    {
        id: 23,
        src: 'main(23).jpg',
        name: 'Ruang 23'
    },

    {
        id: 24,
        src: 'masjid.jpg',
        name: 'Masjid AL BAROKAH'
    },

    {
        id: 25,
        src: 'parkiran.jpg',
        name: 'Tempat Parkir '
    },

    {
        id: 26,
        src: 'perpus.jpg',
        name: 'Perpustakaan'
    },

    {
        id: 27,
        src: 'technopark.jpg',
        name: 'Techno Park'
    },

    {
        id: 28,
        src: 'main(24).jpg',
        name: 'RPS RPL 1'
    },

    {
        id: 29,
        src: 'main(25).jpg',
        name: 'RPS RPL 2'
    },

    {
        id: 30,
        src: 'main(26).jpg',
        name: 'RPS RPL 3'
    },

    {
        id: 31,
        src: 'main(27).jpg',
        name: 'RPS TKJ 1'
    },

    {
        id: 32,
        src: 'main(28).jpg',
        name: 'RPS TKJ 2'
    },

    {
        id: 33,
        src: 'main(29).jpg',
        name: 'RPS TSM 1'
    },

    {
        id: 34,
        src: 'main(30).jpg',
        name: 'RPS TSM 2'
    },
])

</script>

<style lang="scss" scoped></style>