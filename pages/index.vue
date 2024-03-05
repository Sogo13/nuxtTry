<template>
  <div>
    <h1>Drag and Drop Example</h1>
    <DraggableList />
  </div>
</template>

<script>
import DraggableList from '@/components/DraggableList.vue';
export default {
  name: 'IndexPage',
  components: {
    DraggableList,
  },
}
</script>
