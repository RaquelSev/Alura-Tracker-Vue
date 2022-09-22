<template>
  <FormularioTarefa @aoSalvarTarefa="salvarTarefa" />
  <div class="lista">
    <BoxDafult v-if="listaEstaVazia">
      Você não está muito produtivo hoje ):
    </BoxDafult>
    <TarefaLista
      v-for="(tarefa, index) in tarefas"
      :key="index"
      :tarefa="tarefa"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import FormularioTarefa from "../components/FormularioTarefa.vue";
import TarefaLista from "../components/TarefaLista.vue";
import ITarefa from "../interfaces/ITarefa";
import BoxDafult from "../components/BoxDafult.vue";

export default defineComponent({
  name: "App",
  components: {
    FormularioTarefa,
    TarefaLista,
    BoxDafult,
  },
  data() {
    return {
      tarefas: [] as ITarefa[],
    };
  },
  computed: {
    listaEstaVazia(): boolean {
      return this.tarefas.length === 0;
    },
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    },
  },
});
</script>
