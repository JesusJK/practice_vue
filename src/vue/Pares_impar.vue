<script setup>
import { ref } from 'vue';

const setnumber = ref([]);

const numbers = ref([]);
const number_par = ref([]);
const number_impar = ref([]);

function sendn() {
    numbers.value.push(setnumber.value)

}

function esPar(num) {
    return num % 2 === 0;
}

function esImpar(num) {
    return num % 2 !== 0;
}  

function n_par() {
    number_par.value = numbers.value.filter(esPar);         //filter para filtrar segun una función
}

function n_impar() {
    number_impar.value = numbers.value.filter(esImpar);
}

</script>

<template>
    <div class="bg-slate-300 shadow rounded mx-auto mt-1 px-8 py-10">

        <div id="introducir" class="m-2">
            <input v-model="setnumber" placeholder="Introducir un numero" type="number" class="font-semibold m-1 p-1">

            <button @click="sendn()" class="bg-gray-500 text-white p-2 rounded mx-1">Enviar</button>

            <button @click="n_par()" class="text-white border rounded p-1 m-2 w-[50px] bg-green-500">Par</button>
            <button @click="n_impar()" class="text-white border rounded p-1 m-2 bg-red-500">Impar</button>
        </div>


        <div id="pantalla" class="bg-white flex justify-between">
            <div id="par" class="border-gray-600 border mx-1 w-[50%]">
                <strong class="flex justify-center">Numeros Pares</strong>
                <div v-for="(number, index) in number_par" :key="index" class="bg-white/60 px-2">
                    {{ number }}
                </div>

            </div>

            <div id="impar" class="border-gray-600 border mx-1 w-[50%]">
                <strong class="flex justify-center">Numeros Impares</strong>
                <div v-for="(number, index) in number_impar" :key="index" class="bg-white/60 px-2">
                    {{ number }}
                </div>
            </div>

        </div>




    </div>
</template>