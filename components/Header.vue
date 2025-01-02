<template>
    <div class="header z-20 sticky w-screen flex justify-center items-center p-5 h-[100%] font-playfair">
        <div>
            <img class="flex justify-start max-w-[200px]" src="../assets/img/logo smkn 4.png" alt="">
        </div>


        <div class="menu text-[18px]">
            <ul>
                <li>
                    <NuxtLink to="/">Beranda</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="../artikel">Artikel</NuxtLink>
                </li>
                <li>
                    <a class="w-full" href="#">Profil Sekolah</a>
                    <ul>
                        <li>
                            <NuxtLink to="/profilsekolah/history">Sejarah</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/profilsekolah/visimisi">Visi Misi</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/profilsekolah/identitas">Identitas Sekolah</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/profilsekolah/gurustaff">Guru dan Staff</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/profilsekolah/statistik">Data statistik</NuxtLink>
                        </li>
                    </ul>
                </li>
                <li>
                    <NuxtLink to="../galery">Galeri</NuxtLink>
                </li>
                <li>
                    <a class="w-full" href="#">Siswa</a>
                    <ul>
                        <li>
                            <NuxtLink to="/siswa/programkeahlian">Program Keahlian</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/siswa/ekskul">Ekstrakulikuler</NuxtLink>
                        </li>
                    </ul>
                </li>
                <li>
                    <a class="w-full" href="#">Sarana Prasarana</a>
                    <ul>
                        <li><NuxtLink to="/sapras/tanah">Tanah</NuxtLink></li>
                        <li><NuxtLink to="/sapras/ruangan">Ruang Kelas dan Praktek</NuxtLink></li>
                    </ul>
                </li>
            </ul>
        </div>
    </div>

</template>


<style scoped>
.header {
    background: linear-gradient(180deg, #011a3b, #033d8c);
}

.menu {
    border-radius: 6px;
}

.menu ul {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}

.menu ul li {
    list-style: none;
    padding: 4px;
    position: relative;
    transition: 0.5s;
    display: block;
}

.menu ul li a {
    color: white;
    text-decoration: none;
    padding: 5px 10px;
}

.menu ul li a:hover {
    color: #ffad00;
    border-radius: 6px;
    transition: ease-in-out 600ms;
}

.menu ul li ul {
    display: none;
}

.menu ul li:hover ul {
    display: block;
    position: absolute;
    margin-top: 5px;
    background: linear-gradient(180deg, #011a3b, #033d8c);
    border-radius: 6px;
    box-shadow: 0px 20px 100px 0px rgba(0, 0, 0, 0.5);
    width: max-content;
    padding-top: 5px;
    padding-bottom: 5px;
    transition: ease-in-out 900ms;
}

.menu ul li ul a {
    color: white;
    padding-left: 10px;
    margin: 0;
}

.menu ul li ul a:hover {
    color: #ffad00;
}
</style>
