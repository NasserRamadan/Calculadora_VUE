<script setup>
const props = defineProps(["valorNumero1", "valorNumero2", "trocarFiltro"]);

const emit = defineEmits(["update:valorNumero1", "update:valorNumero2", "update:trocarFiltro"]);

const handleNumero1Change = (event) => {
  emit("update:valorNumero1", Number(event.target.value));
};

const handleNumero2Change = (event) => {
  emit("update:valorNumero2", Number(event.target.value));
};

const handleFiltroChange = (event) => {
  emit("update:trocarFiltro", event.target.value);
};
</script>

<template>
  <form>
    <div class="row d-flex align-items-center">
      <div class="col gap-2 d-flex">
        <input @input="handleNumero1Change" class="form-control" type="number" />
        <input @input="handleNumero2Change" class="form-control" type="number" />
      </div>
      <div class="col">
        <select @change="handleFiltroChange" class="form-control text-center">
          <option value="multiplicacao">Multiplicação</option>
          <option value="adicao">Adição</option>
          <option value="subtracao">Subtração</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
    </div>
  </form>
</template>
