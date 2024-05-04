<template>
  <div>
    <!-- Judul -->
    <h1>Selamat Datang di K-Pop!</h1>

    <!-- Deskripsi grup -->
    <p :style="{ color: textColor }">{{ groupDescription }}</p>

    <!-- Daftar member grup -->
    <h2>Member Grup:</h2>
    <ul>
      <li v-for="member in groupMembers" :key="member">{{ member }}</li>
    </ul>

    <!-- Elemen input teks untuk mengubah deskripsi -->
    <input v-model="newDescription" placeholder="Masukkan deskripsi baru" />

    <!-- Tombol untuk mengubah deskripsi grup -->
    <button @click="changeDescription" :class="{ 'text-pink': buttonTextColor === 'pink', 'bg-pink': buttonBackgroundColor === 'pink' }">Ubah Deskripsi</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      groupDescription: 'Ini adalah deskripsi grup K-pop.', // Deskripsi grup K-pop
      groupMembers: ['Jennie', 'Lisa', 'Jisoo', 'Rose'], // Daftar member grup K-pop
      newDescription: '', // Variabel untuk menyimpan deskripsi baru
      textColor: 'black', // Warna teks deskripsi
      buttonTextColor: 'black', // Warna teks tombol "Ubah Deskripsi"
      buttonBackgroundColor: 'transparent' // Warna latar belakang tombol "Ubah Deskripsi"
    };
  },
  methods: {
    // Fungsi untuk mengubah deskripsi grup
    changeDescription() {
      if (this.newDescription.trim() !== '') {
        this.groupDescription = this.newDescription;
        this.newDescription = ''; // Reset input teks setelah diubah
        this.textColor = 'brown'; // Ubah warna teks deskripsi setelah diubah
        this.buttonTextColor = 'black'; // Ubah warna teks tombol "Ubah Deskripsi" ketika ditekan
        this.buttonBackgroundColor = 'pink'; // Ubah warna latar belakang tombol "Ubah Deskripsi" ketika ditekan
      }
    }
  }
};
</script>

<style scoped>
/* Style untuk halaman web */
h1 {
  color: #db5c8f;
}

.text-pink {
  color: pink;
}

.bg-pink {
  background-color: pink;
}
</style>
