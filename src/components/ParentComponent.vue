<template>
  <div>
    <h1 class="parent-title">Parent Component</h1>
    <p>Data dari Child: {{ childData }}</p>

    <!-- Menggunakan Slot -->
    <slot></slot>

    <ChildComponent1 @child1Event="handleChild1Event" />
    <ChildComponent2 @child2Event="handleChild2Event" />
  </div>
</template>

<script>
import ChildComponent1 from './ChildComponent1.vue';
import ChildComponent2 from './ChildComponent2.vue';

export default {
  name: 'ParentComponent',
  components: {
    ChildComponent1,
    ChildComponent2
  },
  data() {
    return {
      childData: ''
    };
  },
  methods: {
    handleChild1Event(data) {
      this.childData = data;
    },
    handleChild2Event(data) {
      this.childData = data;
    }
  }
}
</script>

<style scoped>
.parent-title {
  font-size: 32px;
  color: #2d4059; /* Warna biru tua */
  margin-bottom: 20px;
  text-align: center;
}

/* Styling untuk slot */
.slot-content {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 15px;
  background-color: #f9f9f9;
  margin-top: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.slot-content h2 {
  font-size: 20px;
  color: #2d4059; /* Warna biru tua */
  margin-bottom: 10px;
}

.slot-content p {
  color: #666;
  line-height: 1.5;
}

/* Style untuk Child Components */
.child-component {
  margin-top: 20px;
  text-align: center;
}

.child-component button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.child-component button:hover {
  background-color: #0056b3;
}
</style>
