<template>
  <div class="myApp">
    <h1>Ваш менеджер задач</h1>
    <NuxtLink to="/healthCare">
    <h2 class="tryDiagrams" >Не забудьте отметить ваше самочувствие!</h2>
    </NuxtLink>
    <div class="createInp">
      <div class="createInput">
        <input v-model="item" class="createInputString"  placeholder="Введите вашу задачу" @keydown.enter="addItem">
        <p class="createInputIcon" @click="addItem" >+</p>
      </div>
    </div>
    <div>
    <h2 class="dragHeader">Мои задачи по приоритету</h2>
    </div>
    <DraggableList :tasks="tasks"/>
  </div>
</template>

<script>
import DraggableList from '@/components/DraggableList.vue';
export default {
  name: 'IndexPage',
  components: {
    DraggableList,
  },
  data(){
    return{
    item:'',
      tasks:[],
    }
  },

  methods:{
    addItem(){
      if (this.item.length){
        this.tasks.push(this.item)
      }
      this.item = ''
    },
    goDiagrams(){
      this.$router.push({name:'diagrams'})
    }
  }
}
</script>
<style >
.myApp{
  position: relative;
 text-align: center;
}
.tryDiagrams{
  position: absolute;
  top: 2%;
 margin: 0;
  right: 3%;
}
.createInp{
  display: flex;
  justify-content: center;
}
.createInput{
width: 50%;
border: 1px solid black ;
  display: flex;

}
.createInputString{
  padding: 16px;
width: 90%;
  outline: none;
  border: none;
}
.createInputIcon{
  font-size: 25px;
}
.dragHeader{
  padding:16px ;
}
</style>
