<script setup>
const props = defineProps(['num1', 'num2', 'operacao'])
const emit = defineEmits(['update:num1', 'update:num2', 'update:operacao'])
</script>

<template>
    <form>
    <div class="d-flex align-items-center gap-2">
        <!-- Primeiro número -->
        <input
        class="form-control"
        type="number"
        placeholder="Número 1"
        :value="num1"
        @input="emit('update:num1', parseFloat($event.target.value))"
        />

        <!-- Operação -->
        <select
        class="form-select"
        :value="operacao"
        @change="emit('update:operacao', $event.target.value)"
        style="width: 80px;"
        >
        <option value="adicao">+</option>
        <option value="subtracao">−</option>
        <option value="multiplicacao">×</option>
        <option value="divisao">÷</option>
        </select>

        <!-- Segundo número -->
        <input
        class="form-control"
        type="number"
        placeholder="Número 2"
        :value="num2"
        @input="emit('update:num2', parseFloat($event.target.value))"
        />
    </div>
    </form>
</template>