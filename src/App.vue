<script setup>
import { ref, computed } from 'vue'

const taches = ref([])
const nouvelleTache = ref('')
const tachesRestantes = computed(() => {
    return taches.value.filter(tache => !tache.terminee).length
})
function ajouterTache() 
{
  if (nouvelleTache.value.trim() === '') 
  {
    return
  }
  taches.value.push({
    id: Date.now(),
    libelle: nouvelleTache.value,
    terminee: false
})
  nouvelleTache.value = ''
}

function supprimerTache(id) 
{
    taches.value = taches.value.filter(tache => tache.id !== id)
}
</script>

<template>
  <h1>Gestion des tâches</h1>

<form @submit.prevent="ajouterTache">
  <input v-model="nouvelleTache" type="text" placeholder="Nom de la tâche"/>
  <button type="submit">Ajouter</button>
</form>

  <p v-if="taches.length === 0">
  Aucune tâche pour le moment.
</p>
  <div v-for="tache in taches" :key="tache.id" class="task">
      <input type="checkbox" v-model="tache.terminee"/>
    <span :class="{ terminee: tache.terminee }">
      {{ tache.libelle }}
  </span>
    <button @click="supprimerTache(tache.id)">Supprimer</button>

  </div>
  <p class="compteur">
  {{ tachesRestantes }} tâche(s) non terminée(s)
</p>

</template>
<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
}

#app {
  max-width: 600px;
  margin: 50px auto;
  padding: 30px;
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
}

form {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

form input {
  flex: 1;
  padding: 10px;
}

button {
  padding: 10px 15px;
  cursor: pointer;
}

.task {
  display: flex;
  align-items: center;
  gap: 10px;
  margin: 10px 0;
  padding: 10px;
  border-bottom: 1px solid #ddd;
}

.task span {
  flex: 1;
}

.terminee {
  text-decoration: line-through;
}

.compteur {
  margin-top: 20px;
  font-weight: bold;
}
</style>