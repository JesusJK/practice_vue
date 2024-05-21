<script setup>
import { ref } from 'vue';

const numbers = ref([]);
const setnumber = ref('');

function sendn() {
    numbers.value.push(setnumber.value)
    console.log(numbers)
}

function n_par() {
    for (let i = 0; i < numbers.length; i++) {
        if (numbers[i] % 2 == 0) {
            const n_pares = ([numbers[i]])
        }
        
    }
}

function n_impar() {
    
}


</script>

<template>
    <div class="bg-slate-300 shadow rounded mx-auto mt-1 px-8 py-10">

        <div id="introducir" class="m-2">
            <button @click="sendn()" class="bg-gray-500 text-white p-2 rounded mx-1">Enviar</button>
            <input v-model="setnumber" placeholder="Introducir un numero" type="number" class="font-semibold m-1 p-1">
            <button @click="n_par()" class="text-white border rounded p-1 m-2 w-[50px] bg-green-500">Par</button>
            <button @click="n_impar()" class="text-white border rounded p-1 m-2 bg-red-500">Impar</button>
        </div>


        <div id="pantalla" class="bg-white flex justify-between">
            <div id="par" class="border-gray-600 border mx-1 w-[50%]">
                <Strong class="flex justify-center">Numeros Pares</Strong>
                        <div v-for="(num, index) in numbers" :key="index" class="bg-white/60 px-2">{{ numbers }}</div>
                  
            </div>

            <div id="impar" class="border-gray-600 border mx-1 w-[50%]">
                <strong class="flex justify-center">Numeros Impares</strong>
                <ul>
                    <li></li>
                </ul>
            </div>

        </div>




    </div>
</template>