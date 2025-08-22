<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-buttons slot="start">
                    <ion-back-button default-href="/tabs/tab3"></ion-back-button>
                </ion-buttons>
                <ion-title>{{ gameData ? gameData.name : 'Detail Game' }}</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content :fullscreen="true">
            <div v-if="gameData" class="ion-padding">
                <h1>{{ gameData.name }}</h1>
                <p>{{ gameData.description }}</p>
                <img :src="`/${route.params.id}.jpg`" alt="Gambar Game" style="max-width: 300px;">
            </div>
        </ion-content>
    </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButtons, IonBackButton } from '@ionic/vue';
import { useRoute } from 'vue-router';
import { computed } from 'vue';


const gamesDatabase: { [key: string]: any } = {
    'pokemon': {
        name: 'Pokemon',
        description: 'Pokémon, singkatan dari "Pocket Monsters", adalah seri permainan video bergenre Role-Playing Game (RPG). Konsep utamanya adalah menangkap, melatih, dan mempertarungkan makhluk-makhluk fiksi yang disebut Pokémon. Pemain berperan sebagai seorang Pokémon Trainer yang berkeliling dunia untuk mengumpulkan berbagai jenis Pokémon, melatih mereka agar menjadi lebih kuat dan berevolusi, serta mengalahkan pelatih lain dalam pertarungan berbasis giliran (turn-based). Tujuan utamanya adalah menjadi juara Pokémon League dengan mengalahkan delapan Gym Leader dan kelompok elit Elite Four, sambil juga berusaha melengkapi Pokédex, sebuah ensiklopedia digital yang mencatat semua Pokémon yang pernah ditemui dan ditangkap.',
    },
    'megaman': {
        name: 'Mega Man ',
        description: 'Mega Man adalah seri permainan video aksi-platformer klasik yang terkenal dengan tingkat kesulitannya yang menantang. Pemain mengontrol Mega Man, seorang robot humanoid biru yang bertarung melawan ilmuwan jahat Dr. Wily dan pasukan "Robot Masters" ciptaannya. Gameplay utamanya adalah berlari, melompat, dan menembak musuh di berbagai level yang penuh rintangan. Keunikan dari seri ini adalah pemain bisa memilih level mana yang ingin diselesaikan terlebih dahulu. Setelah mengalahkan seorang bos (Robot Master), Mega Man akan menyerap kekuatan dan senjata unik bos tersebut, yang kemudian bisa digunakan untuk mengeksploitasi kelemahan bos lainnya.',
        
    },
    'zelda': {
        name: 'The Legend of Zelda',
        description: 'The Legend of Zelda adalah seri permainan aksi-petualangan (action-adventure) yang berlatar di dunia fantasi bernama Hyrule. Pemain umumnya mengendalikan seorang pahlawan muda bernama Link dalam misinya untuk menyelamatkan Putri Zelda dan Kerajaan Hyrule dari cengkeraman penjahat utama, Ganon (atau Ganondorf). Gameplay seri ini merupakan perpaduan antara eksplorasi dunia yang luas, pertarungan melawan monster secara real-time, dan pemecahan teka-teki yang cerdas di dalam kuil atau dungeon. Elemen kunci dari permainan ini adalah menemukan item-item baru (seperti busur, bom, atau hookshot) yang tidak hanya membantu dalam pertarungan tetapi juga membuka akses ke area-area baru di dunia permainan.',
    },
    'pac-man': {
        name: 'Pac-Man',
        description: 'Pac-Man adalah salah satu permainan arkade paling ikonik sepanjang masa. Gameplay-nya sangat sederhana namun adiktif. Pemain mengontrol karakter kuning bernama Pac-Man di dalam sebuah labirin. Tujuannya adalah untuk "memakan" semua titik kecil (disebut Pac-Dots) di dalam labirin sambil menghindari empat hantu berwarna yang terus mengejarnya. Di empat sudut labirin, terdapat Power Pellet berukuran lebih besar. Jika Pac-Man memakannya, para hantu akan berubah menjadi biru dan rentan untuk sementara waktu, memungkinkan Pac-Man untuk memakan mereka demi mendapatkan poin bonus. Permainan berakhir jika Pac-Man tertangkap oleh hantu..',
    },
    'super-mario': {
        name: 'Super Mario',
        description: 'Super Mario (khususnya game seperti Super Mario World) adalah seri permainan platformer yang menjadi standar bagi genre ini. Pemain mengontrol Mario (atau saudaranya, Luigi) dalam sebuah petualangan untuk menyelamatkan Putri Peach dari Bowser, sang Raja Koopa. Gameplay-nya berpusat pada berlari dan melompat melewati berbagai rintangan dan platform di Kerajaan Jamur. Mario dapat mengalahkan musuh dengan menginjak kepala mereka dan bisa mendapatkan berbagai power-up ikonik, seperti Jamur Super untuk membuatnya lebih besar, Bunga Api untuk menembakkan bola api, dan Jubah Terbang (di Super Mario World) untuk melayang di udara. Setiap level memiliki tujuan untuk mencapai tiang bendera di akhir, dan sering kali memiliki jalan rahasia dan koleksi tersembunyi yang mendorong pemain untuk bereksplorasi.',
    }
};


const route = useRoute();


const gameData = computed(() => {
    const gameId = route.params.id as string;
    return gamesDatabase[gameId];
});
</script>