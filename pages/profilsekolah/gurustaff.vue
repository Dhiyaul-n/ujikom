<template>
    <div class="container mx-auto">
        <h1 class="text-[50px] text-center font-playfair font-medium mt-20">Guru dan Staff</h1>
        <h1 class="text-[20px] text-center text-[#ababab] font-medium">Total Guru: {{ db_teachers.length }}</h1>

        <!-- Search Field -->
        <div class="flex justify-center my-5">
            <input v-model="searchQuery" class="border rounded-lg p-2 w-1/3" type="text"
                placeholder="Cari guru berdasarkan nama..." @input="filterByName" />
        </div>

        <!-- Teachers Grid -->
        <div class="grid grid-cols-3 gap-4">
            <v-card v-for="teacher in teachers" :key="teacher.id" class="mx-auto my-10" width="300">
                <img class="rounded-2xl 1:1 " :src="`/img/teacher/${teacher.src}`" alt="Teacher Image">
                <v-card-title class="text-center">{{ teacher.name }}</v-card-title>
                <v-card-subtitle class="text-center">{{ teacher.subject || 'Mata Pelajaran Belum Di isi'
                    }}</v-card-subtitle>
            </v-card>
        </div>

        <!-- Action Buttons -->
        <div class="flex justify-between items-center my-5">
            <button class="flex items-center max-w-[200px] h-[100%] max-h-10 text-center bg-[#ddd] rounded-lg p-4"
                @click="loadMore">
                Load More
            </button>
            <button class="flex items-center max-w-[200px] h-[100%] max-h-10 text-center bg-[#ddd] rounded-lg p-4"
                @click="loadAll">
                Load All
            </button>
            <button class="flex items-center max-w-[200px] h-[100%] max-h-10 text-center bg-[#ddd] rounded-lg p-4"
                @click="loadLess">
                Load Less
            </button>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

// Teachers data
const db_teachers = ref([
    {
        id: 1,
        name: 'Kurniawan, S.Pd., M.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 2,
        name: 'Dini Dartini, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 3,
        name: 'Hj. Lilis Suryani, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 4,
        name: 'Saepudin, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 9,
        name: 'Ekawati, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 6,
        name: 'Isep Wartiman, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 7,
        name: 'Nia Kurniawati, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 8,
        name: 'Ayi Kurnia, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 9,
        name: 'Ema Jatnika, M.Kom.',
        subject: '',
        src: '',
    },
    {
        id: 10,
        name: 'Hj. Sri Agustina, S.Pd., M.Pd.',
        subject: '',
        src: 'sri.jpg',
    },
    {
        id: 11,
        name: 'Imat Ruhimat, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 12,
        name: 'Hj. Ai Nurhayati, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 13,
        name: 'Epi Puspitasari, S.Pd., M.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 14,
        name: 'Kadarsah, S.Kom.',
        subject: '',
        src: '',
    },
    {
        id: 15,
        name: 'Aceng Saripudin, S.Si., M.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 16,
        name: 'Laela Badriah, S.Pd.I.',
        subject: '',
        src: '',
    },
    {
        id: 17,
        name: 'Evy Susanti, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 18,
        name: 'Dede Irawan, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 19,
        name: 'Sifa Utami, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 20,
        name: 'Fikri A. Yudhistira, S.T., M.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 21,
        name: 'Arip, S.T., M.Kom.',
        subject: '',
        src: 'arip.jpg',
    },
    {
        id: 22,
        name: 'Ali Saeful Milah, S.Kom.',
        subject: '',
        src: '',
    },
    {
        id: 23,
        name: 'Lestari Noer Aisyah, S.Pd., M.IL.',
        subject: '',
        src: '',
    },
    {
        id: 24,
        name: 'Ade Rohmat, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 25,
        name: 'Muliadi, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 26,
        name: 'Budi Setiadi, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 27,
        name: 'Wawan Setiawan, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 28,
        name: 'Taufik Hidayat, S.Kom.',
        subject: '',
        src: 'taufik.jpg',
    },
    {
        id: 29,
        name: 'Fajri Ash-shiddiqi, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 30,
        name: 'Ryndi Mardoh, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 31,
        name: 'R. Tini Gantini, S.H.',
        subject: '',
        src: 'tini.jpg',
    },
    {
        id: 32,
        name: 'Lisye Diana Inggriani, S.Kom.',
        subject: '',
        src: 'lisye.jpg',
    },
    {
        id: 33,
        name: 'Yusep Saepul Wahyu, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 34,
        name: 'Suminar, M.Kom.',
        subject: '',
        src: 'suminar.jpg',
    },
    {
        id: 35,
        name: 'Helmi Permana, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 36,
        name: 'Jajang Deta Mulyadi, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 37,
        name: 'Deni Maulana, S.T.',
        subject: '',
        src: 'deni.jpg',
    },
    {
        id: 38,
        name: 'Novi Abdul Rohman, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 39,
        name: 'Imas Masruroh, S.T.',
        subject: '',
        src: 'joy.jpg',
    },
    {
        id: 40,
        name: 'Andi Moh Permadi, S.Kom.',
        subject: '',
        src: 'andi.jpg',
    },
    {
        id: 41,
        name: 'Siti Nurmalah, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 42,
        name: 'Ami Miftahul Lukman N., S.T.',
        subject: '',
        src: '',
    },
    {
        id: 43,
        name: 'Resti Tandiani Utami, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 44,
        name: 'Deri Heryanto, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 45,
        name: 'Adi Iasan, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 46,
        name: 'Airista Jayanti, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 47,
        name: 'Gandi Angriawan, S.Pd.I.',
        subject: '',
        src: 'gandi.jpg',
    },
    {
        id: 48,
        name: 'Anna Rachmiati Hidayat, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 49,
        name: 'Githa Farida, M.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 50,
        name: 'Salman Parisi, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 51,
        name: 'Muhammad Hilmi A., S.Kom.',
        subject: '',
        src: '',
    },
    {
        id: 52,
        name: 'Ana Maulana Malik Ibrahim, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 53,
        name: 'Dian Suryatin, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 54,
        name: 'Eki Rizki Ramdani, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 55,
        name: 'A. Yusup Hanafi, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 56,
        name: 'Nita Marlina, M.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 57,
        name: 'Haryanti Rahmawati, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 58,
        name: 'Muhammad Arief S., SE., S.Kom.',
        subject: '',
        src: '',
    },
    {
        id: 59,
        name: 'Tri Wahyuni, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 60,
        name: 'Zul Hilmi, S.T.',
        subject: '',
        src: 'zul.jpg   ',
    },
    {
        id: 61,
        name: 'Ratih Dwijayanti, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 62,
        name: 'Asep Sholehudin, S.Pd.I.',
        subject: '',
        src: '',
    },
    {
        id: 63,
        name: 'Runi Puspa Amaliah, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 64,
        name: 'Lisna Windi Nurhuda, S.Pd.',
        subject: '',
        src: 'lisna.jpg',
    },
    {
        id: 65,
        name: 'Bintang Anugrahing Widhi, S.T.',
        subject: '',
        src: '',
    },
    {
        id: 66,
        name: 'Euis Nursidah, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 67,
        name: 'Fahmi Fauzie A. S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 68,
        name: 'Amanata Salma, S.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 69,
        name: 'Yen Yen Suryani, S.Pd., M.Pd.',
        subject: '',
        src: '',
    },
    {
        id: 70,
        name: 'Farida Juhara, S.Pd.',
        subject: '',
        src: '',
    },

]);

// State management
const allTeachers = ref([...db_teachers.value]); // Contains all teachers
const teachers = ref([...db_teachers.value.slice(0, 5)]); // Current visible teachers
const limitStart = ref(0);
const limitEndMore = ref(5);
const searchQuery = ref(''); // For dynamic search input


// Load more teachers
const loadMore = () => {
    if (limitEndMore.value >= db_teachers.value.length) return; // Prevent overflow
    limitEndMore.value += 5;
    teachers.value = [...db_teachers.value.slice(0, limitEndMore.value)];
    limitStart.value = limitEndMore.value - 5;
};

// Load less teachers
const loadLess = () => {
    // Ensure we don't reduce beyond the minimum allowed (5)
    if (limitEndMore.value > 5) {
        limitEndMore.value -= 5; // Decrease the end limit
        limitStart.value = Math.max(0, limitEndMore.value - 5); // Adjust start limit to avoid negative values

        // Update the teachers array to the new range
        teachers.value = db_teachers.value.slice(limitStart.value, limitEndMore.value);
    }
};


// Load all teachers
const loadAll = () => {
    teachers.value = [...allTeachers.value];
    limitStart.value = 0;
    limitEndMore.value = allTeachers.value.length;
};

// Filter teachers by name
const filterByName = () => {
    const query = searchQuery.value.trim().toLowerCase(); // Trim whitespace and convert to lowercase
    if (!query) {
        // Reset to the current limited set of teachers if the search query is empty
        teachers.value = db_teachers.value.slice(0, limitEndMore.value);
        return;
    }

    // Filter teachers based on the query (case-insensitive match)
    teachers.value = db_teachers.value.filter((teacher) =>
        teacher.name.toLowerCase().includes(query)
    );

    // Ensure limits are updated based on filtered results
    limitStart.value = 0;
    limitEndMore.value = teachers.value.length;
};

</script>

<style scoped>
.container {
    padding: 1rem;
}
</style>
