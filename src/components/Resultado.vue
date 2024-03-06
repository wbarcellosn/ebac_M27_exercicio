<script setup>

const props = defineProps(['estado']);

</script>

<template>
    <div class="row mt-2 p-2 rounded-4">
      <div class="col-6 mx-auto">
        <p class="text-center">O resultado da operação é:</p>
        <h2 class="text-center">{{ props.estado.resultado }}</h2>
      </div>
    </div>
</template>