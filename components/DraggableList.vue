<template>
  <draggable v-model="items">
    <div v-for="(item, index) in tasks" :key="index" class="item">{{ item }}</div>
  </draggable>
</template>

<script>
import draggable from 'vuedraggable';

export default {

  components: {
    draggable,
  },
  props:['tasks'],
  data() {
    return {
      items: ['Item 1', 'Item 2', 'Item 3'],
    };
  },
};
</script>

<style scoped>
.item {
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  padding: 10px;
  margin: 5px;
}
</style>
