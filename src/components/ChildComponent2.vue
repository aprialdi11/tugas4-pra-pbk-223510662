<template>
  <div>
    <button @click="handleClick">Tekan Aku!</button>
  </div>
</template>

<script>
export default {
  name: 'ChildComponent2',
  methods: {
    handleClick() {
      this.$emit('child2Event', '223510662');
    }
  }
}
</script>

<style scoped>
button {
  padding: 12px 24px; /* Padding diperbesar untuk kenyamanan */
  font-size: 18px; /* Ukuran font diperbesar */
  background: linear-gradient(45deg, #007bff, #00d4ff); /* Gradient warna biru */
  color: #fff; /* Warna teks putih */
  border: none;
  border-radius: 6px; /* Sudut border diperhalus */
  cursor: pointer;
  transition: background 0.3s ease, transform 0.2s ease;
  outline: none; /* Hilangkan garis fokus saat tombol diklik */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Tambahkan bayangan */
  position: relative; /* Posisi relatif untuk efek tambahan */
  overflow: hidden; /* Untuk menyembunyikan elemen pseudo di luar border */
}

button::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 300%;
  height: 300%;
  background: rgba(255, 255, 255, 0.15);
  transform: translate(-50%, -50%) rotate(45deg);
  transition: width 0.3s ease, height 0.3s ease;
  border-radius: 50%;
  z-index: 0;
}

button:hover::before {
  width: 0;
  height: 0;
}

button:hover {
  background: linear-gradient(45deg, #0056b3, #007bff); /* Gradient warna biru gelap */
  transform: translateY(-2px); /* Efek angkat saat hover */
}

button:active {
  transform: translateY(0); /* Efek kembali saat tombol ditekan */
}
</style>
