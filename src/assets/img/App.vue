<script setup lang="ts">
import DecoracaoContainer from './components/DecoracaoContainer.vue';
</script>

<template>

  <main class="d-flex justify-between">
    <section class="decorationContainer">
      <DecoracaoContainer />
    </section>
    <section class="formContainer">campo de login</section>
  </main>
</template>
<style>
main {
  display: flex;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;

}

.decorationContainer {
  display: initial;
  width: 50%;
  background: #CE1728;
  position: relative;
}

.formContainer {
  margin: auto;
  width: 90%;
  max-width: 350px;
}
</style>
