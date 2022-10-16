<template>
   <!-- 
  <contact-info prenom="Brad" nom="PITT" />
  <contact-info prenom="Bruce" nom="WILLIS" /> 
  -->
  <!-- avec property binding j'envoi des variables -->
  <contact-info
  v-for="p in personnes" 
  :prenom="p.prenom" 
  :nom="p.nom"
  :id="p.id"
  :key="p.id"
  @enlever="effacer"
  />
</template>

<script>
// importer le component
import ContactInfo from "./components/ContactInfo.vue";

export default {
  name: "App",
  components: {
    ContactInfo, // Je declare le component
  },
  data() {
    return {
      personnes: [
        { id:42, prenom: "Angelina", nom: "JOLIE" },
        { id:54,prenom: "Simone", nom: "VEIL" },
        { id:22,prenom: "Marie", nom: "CURIE" },
      ],
    };
  },
  methods:{
    effacer(id){
      console.log(id);
      // je viens écrase le tableau de personnes par 
      // 1 nouveau tableau
      //le Nouveau tab = tab moins la personne avec cet ID
      //p.id != id return false 
      //n'ajoute l objet p dans le nouveau tableau
      this.personnes = this.personnes.filter( (p) => p.id !== id) ;
    }
  }
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
