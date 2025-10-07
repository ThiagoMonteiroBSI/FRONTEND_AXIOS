<script setup>
import axios from 'axios';
import { ref } from 'vue';

const produtos = ref([])

async function buscarProdutos() {
   const response = await axios.get('/produtos')
   produtos.value = response.data
}

</script>

<template>
<h1> Listagem de Produtos </h1>
<ul>
    <li v-for="produto in produtos" :key="produto.id">
        {{ produto.nome }} - R$ {{ produto.preco }}
    </li>
</ul>
<button @click="buscarProdutos">Buscar</button>
</template>

<style scoped>

</style>
