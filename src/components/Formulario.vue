<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de tarefas"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar"
          v-model="descricao"
        />
      </div>

      <div class="column">
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Temporizador from "./Temporizador.vue";

export default defineComponent({
  name: "Formulario",
  data() {
    return {
      descricao: "",
    };
  },
  components: {
    Temporizador,
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      this.descricao = "";

      console.log(tempoDecorrido);
      console.log(this.descricao);
    },
  },
});
</script>
