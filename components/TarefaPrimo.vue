<template>
  <BoxPrimo>
    <div class="columns">
      <div class="column is-7">{{ tarefa.descricao || 'Tarefa sem descrição' }}</div>
      <div class="column">
        <CronometroPrimo :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
      </div>
    </div>
  </BoxPrimo>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import CronometroPrimo from "./CronometroPrimo.vue";
import ITarefa from '../interfaces/ITarefa'
import BoxPrimo from './BoxPrimo.vue'

export default defineComponent({
  name: "TarefaPrimo",
  components: {
    CronometroPrimo,
    BoxPrimo
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  }
});
</script>