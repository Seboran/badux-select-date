<script setup lang="ts">
const listeDeDates: { jour: string; mois: string; annee: string }[] = []
for (let annee = 1900; annee <= 2025; annee++) {
  // if annee is leap year
  // janvier
  for (let jour = 0; jour <= 31; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'janvier', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 28; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'février', annee: annee.toString() })
  }
  if (annee % 4 === 0 && (annee % 100 !== 0 || annee % 400 === 0)) {
    listeDeDates.push({ jour: '29', mois: 'février', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 31; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'mars', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 30; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'avril', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 31; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'mai', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 30; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'juin', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 31; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'juillet', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 31; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'août', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 30; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'septembre', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 31; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'octobre', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 30; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'novembre', annee: annee.toString() })
  }
  for (let jour = 0; jour <= 31; jour++) {
    listeDeDates.push({ jour: jour.toString(), mois: 'décembre', annee: annee.toString() })
  }
}
</script>

<template>
  <form>
    <h1>Select a date</h1>
    <template v-for="date in listeDeDates" :key="JSON.stringify(date)">
      <input
        name="date"
        type="radio"
        :id="`date-${date.jour}-${date.mois}-${date.annee}`"
        :value="[date.jour, date.mois, date.annee].join('-')"
      />
      <label :for="`date-${date.jour}-${date.mois}-${date.annee}`">
        {{ date.jour }} {{ date.mois }} {{ date.annee }}
      </label>
    </template>
  </form>
</template>

<style scoped></style>
