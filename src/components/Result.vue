<script setup> 
    const props = defineProps(['resultado'])
</script>

<template>
    <div class="mt-4 text-center">
        <h4>Resultado: {{ resultado }} </h4>
    </div>
</template>