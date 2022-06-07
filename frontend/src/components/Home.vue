<script setup>
    import { computed, ref } from 'vue';
    import {useStore} from 'vuex'
    import { useRouter } from 'vue-router';
    const store = useStore();
    const router = useRouter();
    const newName = ref('')

    const name = computed(() => {
        return store.state.user.name
    })

    const saveName = () => {
        store.dispatch('saveName', newName.value);
        newName.value = '';

        router.push({name:'About'})
    }
</script>

<template>
    <div>
        <h1 class="display-1">HOME</h1>
        <p class="">Name in store is : {{name}}</p>
    </div>
    <div>
        <input type="text" class="p-2 mr-4 border border-gray rounded-600" v-model="newName"/>
        <button @click="saveName" class="btn btn-primary">Submit</button>
    </div>
</template>

<style >
h1 {
    font-family: 'Merienda', cursive;    
    font-size: 48px;
}
p{
    font-family: 'Comfortaa', cursive;
}

</style>