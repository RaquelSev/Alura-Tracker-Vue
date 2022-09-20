<template>
  <BoxDafult>
    <div class="columns">
      <div class="column is-7">
        {{ tarefa.descricao || "Tarefa sem descrição" }}
      </div>
      <div class="column">
        <CronometroTempo :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </BoxDafult>
</template>

<script lang="ts">
import ITarefa from "../interfaces/ITarefa";
import { defineComponent, PropType } from "vue";
import CronometroTempo from "./CronometroTempo.vue";
import BoxDafult from "./BoxDafult.vue";

export default defineComponent({
  name: "TarefaLista",
  components: {
    CronometroTempo,
    BoxDafult,
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true,
    },
  },
});
</script>
