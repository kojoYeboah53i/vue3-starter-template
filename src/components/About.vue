<template>
<div class="container p-4">
        <h2> Result</h2>
  <h1 class="font-bold text-2xl"> {{name}} </h1>
</div>
</template>

<script setup>

  import { useStore } from 'vuex'
  import { computed } from 'vue'

  const store = useStore()

  const name = computed(() => { 
        return store.state.user.name
    })
</script>

<style>

</style>