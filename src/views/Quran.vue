<script src="../assets/quran2.js"></script>

<template>
    <section class="search">
        <div class="inputt">
            <a
                href="https://quranschool.com/list-of-quran-surah/"
                class="listSurah"
                target="_blank"
                >List Surah</a
            >
            <input
                type="number"
                v-model="myinput"
                class="inputan"
                placeholder="Masukkan nomor surah"
            />
            <button @click="cari" class="btn">Cari</button>
        </div>
    </section>

    <section class="surah">
        <div class="suara">
            <p v-if="audio">
                <audio controls class="suaraa">
                    <source :src="audio.audio_url" type="audio/mpeg" />
                    Your browser does not support the audio element.
                </audio>
            </p>
        </div>
        <div class="judull">
            <h1 v-if="namaSurah" class="judul">{{ namaSurah.name_simple }}</h1>
        </div>

        <div class="bis">
            <p class="bismillah">بِسْمِ اللهِ الرَّحْمٰنِ الرَّحِيْمِ</p>
        </div>
    </section>

    <section class="hasil">
        <ul class="lista">
            <li class="ayat" v-for="ayat in ayats" :key="ayat.id">
                {{ ayat.text_uthmani }} {{ ayat.text }}
            </li>
        </ul>
    </section>
</template>

<style src="../assets/quran.css"></style>
