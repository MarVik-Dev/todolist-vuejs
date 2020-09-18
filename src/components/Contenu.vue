<template>
  <div class="container">
    <h1 class="mt-5">Entrer les tâches à réaliser :</h1>
    <form>
      <div class="form-group">
        <input v-model="formData.tache" type="text" id="action" class="form-control" />
      </div>
      <button v-on:click.prevent="creationItem" class="btn btn-primary">Ajouter une tâche</button>
    </form>
    <h2 class="mt-5">Tâches à réaliser :</h2>
    <ul class="liste mt-5">
      <li v-bind:key="index" v-for="(tache,index) in tableauTaches">
        <item v-bind:id="index" v-bind:tache="tache" :suppression="suppression"></item>
      </li>
    </ul>
  </div>
</template>


<script>
import Item from "./Item.vue";
export default {
  name: "Contenu",
  data() {
    return {
      formData: {
        tache: ""
      },
      tableauTaches: ["JavaScript", "VueJS", "HTML", "CSS"]
    };
  },
  methods: {
      creationItem: function() {
          this.tableauTaches.push(this.formData.tache)
          this.formData.tache = ''
      },
      suppression: function(e) {
          console.log(e.target.parentNode.id)
          this.tableauTaches.splice(e.target.parentNode.id, 1)
      }
  },
  components: {
    item: Item
  }
}
</script>



<style>
.liste {
  list-style-type: none;
}
ul {
      align-items: center;
      padding: 0;
}
</style>