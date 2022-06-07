<script setup>
    import { computed } from 'vue';
    import { useStore } from 'vuex';
    const store = useStore()

    const name = computed(() => {
        return store.state.user.name
    })
</script>


<template>
    <p class="font-bold text-2xl">The new store value : {{name}}</p>
</template>


<style>
p{
    font-family: 'Merienda', cursive;  
}
</style>