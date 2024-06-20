<template>
  <div >
    <input v-model="numero1" type="number" placeholder="Número 1" />
    <select v-model="operacao">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
    <input v-model="numero2" type="number" placeholder="Número 2" />
    <p>Resultado: {{ resultado }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case 'soma':
          return this.numero1 + this.numero2;
        case 'subtracao':
          return this.numero1 - this.numero2;
        case 'multiplicacao':
          return this.numero1 * this.numero2;
        case 'divisao':
          return this.numero1 / this.numero2;
        default:
          return 0;
      }
    },
  },
};
</script>
