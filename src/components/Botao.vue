<template>
  <button class="button" @click="aoClique" :disabled="desabilitado">
    <span class="icon">
      <i :class="'fas fa-' + icone"></i>
    </span>
    <span>{{ texto }}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Botao',
  emits: ['botaoClicado'],
  props: {
    icone: {
      type: String,
      required: true,
    },
    texto: {
      type: String,
      required: true,
    },
    desabilitado: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    aoClique() {
      this.$emit('botaoClicado');
    },
  },
});
</script>
