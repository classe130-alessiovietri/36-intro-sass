<script>
/* 
  Per importare ed utilizzare un componente dentro un altro devo SEMPRE seguire questi 3 passi:
  1) Importazione del componente
  2) Dichiarazione del componente
  3) Utilizzo del componente
*/
// 1) Importazione del componente
import AppHeader from './components/AppHeader.vue';

export default {
  data() {
    return { 
      count: 0
    }
  },
  // 2) Dichiarazione del componente
  components: {
    AppHeader
  },
  methods: {
    incrementCount() {
      this.count++;
    }
  }
}
</script>

<template>
  <div>
    <!-- 3) Utilizzo del componente -->
    <AppHeader />
    
    <main>
      <p>
        P figlio diretto di main

        <span>
          Ciao ragazzi
        </span>
      </p>

      <div>
        <p>
          P figlio di main, ma NON diretto
        </p>
        <p>
          P figlio di main, ma NON diretto e NON primo figlio
        </p>
      </div>

      <button @click="incrementCount()">
        {{ count }}
      </button>
    </main>

    <div class="debug">
      Ciao questo ha classe debug
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use 'assets/scss/main' as *;
</style>
