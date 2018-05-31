<template>
  <div id="app">
    <header>
      <h1>VueJS Ipsum Viewer</h1>
    </header>
    <main>
      <section class="sidebar">
        <IpsumList v-bind:selected="selected" v-on:selected="updateSelected" />
      </section>
      <section class="viewer">
        <IpsumViewer v-bind:ipsum="selected" />
      </section>
    </main>
  </div>
</template>

<script>
import IpsumList from './components/IpsumList.vue';
import IpsumViewer from './components/IpsumViewer.vue';

export default {
  data() {
    return { selected: null };
  },
  components: {
    IpsumList,
    IpsumViewer
  },
  methods: {
    updateSelected(ipsum) {
      this.selected = ipsum;
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
