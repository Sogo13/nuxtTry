<template>
  <div>
    <NuxtLink to="/">
      <h2 class="tryDiagrams" >На главную</h2>
    </NuxtLink>
    <h1>Оценка сотрудников</h1>
    <form @submit.prevent="addEmployee">
      <label for="name">ФИО:</label>
      <input id="name" v-model="employee.name" type="text"  required>
      <label for="rating">Оценка (от 1 до 10):</label>
      <input id="rating" v-model.number="employee.rating" type="number"  min="1" max="10" required>
      <button type="submit">Добавить</button>
    </form>
    <ul>
      <li v-for="emp in sortedEmployees" :key="emp.id">
        {{ emp.name }} - {{ emp.rating }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      employee: {
        name: '',
        rating: null
      },
      employees: []
    };
  },
  computed: {
    sortedEmployees() {
      return [...this.employees].sort((a, b) => b.rating - a.rating);
    }
  },
  methods: {
    addEmployee() {
      const newEmployee = {...this.employee};
      this.employees.push(newEmployee);
      this.employee.name = '';
      this.employee.rating = null;
    }
  }
};
</script>
