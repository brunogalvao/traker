<template>
  <button class="button" @click="clicado" :disabled="desabilitado">
    <span>
      <i :class="icone"></i>
    </span>
    <span>{{ texto }}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Botao",
  emits: ["clicado"],
  props: {
    desabilitado: {
      type: Boolean,
    },
    icone: {
      type: String,
      require: true,
    },
    texto: {
      type: String,
      require: true,
    },
  },
  methods: {
    clicado(): void {
      this.$emit("clicado");
    },
  },
});
</script>
