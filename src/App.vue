<template>
  <global-component></global-component>
  <local-component :title="title" @addClick="count += $event">
    <!-- Slot Teste -->
    <template v-slot:header>
      Slot Header
    </template>
    <template v-slot:content>
      Slot content
    </template>
  </local-component>
  <p>Count: {{ count }}</p>
</template>

<script>
import LocalComponent from './components/LocalComponent.vue';
export default {
  data() {
    return {
      title: 'Component Title',
      count: 0,
    };
  },
  methods: {},
  components: {
    LocalComponent,
  },
  computed: {
    computedTitle() {
      return 'Teste ' + this.title;
    },
  },
  //-- hooks de inicialização
  beforeCreate() {
    console.log('beforeCreate', this.title, this.computedTitle);
  },
  created() {
    console.log('created', this.title, this.computedTitle);
  },
  //-- hooks de montagem (inserção no DOM)
  beforeMount() {
    console.log('beforeMount');
  },
  mounted() {
    console.log('mounted');
  },
  //-- hooks de atualizações
  beforeUpdate() {
    console.log('beforeUpdate');
  },
  updated() {
    console.log('updated');
  },

  //-- hooks de destruição
  beforeUnmount() {
    console.log('beforeUnmount');
  },
  unmounted() {
    console.log('unmounted');
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
