<template>
  <div>
    <button @click="handleClick">Klik Aku!</button>
  </div>
</template>

<script>
export default {
  name: 'ChildComponent1',
  methods: {
    handleClick() {
      this.$emit('child1Event', 'Aprialdi Nurhidayat');
    }
  }
}
</script>

<style scoped>
button {
  padding: 12px 24px; /* Padding diperbesar untuk kenyamanan */
  font-size: 18px; /* Ukuran font diperbesar */
  background-color: #ff5722; /* Warna oranye */
  color: #fff; /* Warna teks putih */
  border: none;
  border-radius: 6px; /* Sudut border diperhalus */
  cursor: pointer;
  transition: background-color 0.3s ease;
  outline: none; /* Hilangkan garis fokus saat tombol diklik */
  position: relative; /* Gunakan posisi relatif untuk efek shadow */
}

button:hover {
  background-color: #f4511e; /* Warna oranye gelap saat hover */
}

/* Efek Shadow */
button::before {
  content: '';
  position: absolute;
  top: 2px; /* Geser bayangan sedikit ke bawah */
  left: 2px; /* Geser bayangan sedikit ke kanan */
  width: calc(100% - 4px); /* Lebar bayangan berkurang agar tidak tumpang tindih dengan tombol */
  height: calc(100% - 4px); /* Tinggi bayangan berkurang agar tidak tumpang tindih dengan tombol */
  background-color: rgba(0, 0, 0, 0.2); /* Efek shadow */
  border-radius: 6px; /* Sudut border diperhalus */
  z-index: -1; /* Letakkan di bawah tombol */
  transition: opacity 0.3s ease; /* Animasi opasitas saat hover */
  opacity: 0; /* Mulai dengan opacity 0 */
}

button:hover::before {
  opacity: 1; /* Tampilkan bayangan saat tombol dihover */
}
</style>
