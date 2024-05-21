<script setup>
import { ref } from "vue";

const items = ref([
    { title: "Tema 1", subtitle: "Texto del tema 1", estado: false },
    { title: "Tema 2", subtitle: "Texto del tema 2", estado: false },
    { title: "Tema 3", subtitle: "Texto del tema 3", estado: false },
    { title: "Tema 4", subtitle: "Texto del tema 4", estado: false },
    { title: "Tema 5", subtitle: "Texto del tema 5", estado: false },
]);

let tip_grid = ref('');

function abrir(index) {
    items.value[index].estado = !items.value[index].estado;
    for (let i = 0; i < items.length; i++) {
        if (i !== index) {
            items.value[i].estado = false;
        }    
    }
}

function organizar_columnas() {
    tip_grid.value = '';
}

function organizar_filas() {
    tip_grid.value = 'grid grid-cols-4'
}

</script>

<template>
    <div class="border-gray-500 border ">
        <div>
            <div class="mb-1 py-1 px-1 flex justify-center text-center">
                <div class="mb-1 my-1 mx-1 p-2 border-gray-600 border-2"><button
                        @click="organizar_columnas">Columna</button></div>
                <div class="mb-1 my-1 mx-1 p-2 border-gray-600 border-2"><button
                        @click="organizar_filas">Filas</button>
                </div>
            </div>
            <ul :class="tip_grid" class="text-center">
                <li v-for="(item, index) in items" :key="index" class="">
                    <button @click="abrir(index)"
                        class="flex justify-center items-center text-center p-2 mx-auto w-max border-gray-600 border ">
                        {{ item.title }} <span>{{ item.estado ? '-':'+' }}</span></button>
                    <div v-show="item.estado"
                        class=" flex justify-center items-center text-center p-2 mx-auto w-max ">
                        dale
                    </div>
                </li>

            </ul>
        </div>
    </div>

</template>