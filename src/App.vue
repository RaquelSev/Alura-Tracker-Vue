<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
      <FormularioTarefa />
    </div>
    <div class="column is-three-quarter"></div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BarraLateral from "./components/BarraLateral.vue";
import FormularioTarefa from "./components/FormularioTarefa.vue";

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
    FormularioTarefa,
  },
});
</script>

<style></style>
