<template>
  <div id="app">
    <ParentComponent>
      <template v-slot>
        <h2>Data atau Komponen yang Disisipkan</h2>
        <p>Ini adalah konten yang disisipkan dari parent melalui slot.</p>
      </template>
    </ParentComponent>
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  name: 'App',
  components: {
    ParentComponent
  }
}
</script>

<style>
/* App.vue */
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f0f0f0; /* Warna latar belakang */
}

/* ParentComponent.vue */
.parent-container {
  border: 2px solid #ddd;
  border-radius: 10px;
  padding: 20px;
  background-color: #ffffff; /* Warna latar belakang */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  max-width: 500px;
  margin: auto;
}

.child-content {
  margin-top: 20px;
}

/* ChildComponent1.vue dan ChildComponent2.vue */
button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  outline: none; /* menghilangkan garis focus saat button diklik */
}

button:hover {
  background-color: #0056b3;
}

/* Styling untuk slot */
.slot-content {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 10px;
  background-color: #f9f9f9;
  margin-top: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Style untuk judul */
h2 {
  margin-top: 0;
  color: #333;
}

/* Style untuk teks */
p {
  color: #666;
  line-height: 1.5;
}

</style>
