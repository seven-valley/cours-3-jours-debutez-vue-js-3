<template>
hello contact {{id}} {{ prenom }} {{nom}}
<button @click="$emit('enlever',id)">enlever </button>
<br>
<br>
</template>

<script>
export default {
  name: 'ContactInfo',
  emits:['enlever'], // declarer
  props:{
    prenom:String,
    nom:String,
    id:Number
  }
}
</script>