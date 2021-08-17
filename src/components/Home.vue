<template>

  <div class="container mx-auto">
    <h1 class="mb-6 text-3xl font-extrabold">Home</h1>

  <p class="mb-6"> Name in store is {{ name }} </p>
  <input v-model="newName" type="text" class="p-2 border border-gray-600 rounded" />
    <button @click="saveName" class="p-2 rounded ml-5 text-white bg-purple-600"> Submit</button>
  </div>
</template>

<script setup>
// export default {

    import { useStore } from 'vuex'
    import { computed, ref } from 'vue'
    import { useRouter} from 'vue-router'

    const router = useRouter();


    const store = useStore()

    const name = computed(() => { 
        return store.state.user.name
    })

    const newName = ref('')

    const saveName = () => {
        store.dispatch('saveName', newName.value)
        newName.value = ''
        router.push('/about')
    }


// }
</script>

<style>

</style>