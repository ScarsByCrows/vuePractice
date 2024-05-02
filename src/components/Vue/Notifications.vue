<script setup>
import { ref } from 'vue'

const counter = ref(0)

function decrement() {
    if (counter.value > 0) {
        counter.value--
    }
}

function increment() {
    counter.value++
}
</script>

<template>
    <div class="flex-col bg-slate-200 rounded py-8 px-6 w-96 shadow-md flex items-center justify-center">
        <div class="relative">
            <img class="size-32 rounded-full" src="/oc4.png" alt="Foto" />
            <div v-show="counter > 0"
                class="top-0 right-0 flex justify-center items-center size-6 rounded-full bg-red-500 text-white absolute">
                {{ counter }}
            </div>
        </div>
        <p v-if="counter > 0">Tienes Nuevos Mensajes! 🤠</p>
        <p v-else>Mátate sapo perro 😉</p>
        <div class="flex justify-around w-24">
            <button @click="decrement()" class="bg-blue-200 rounded items-center px-2 w-6">
                -
            </button>
            {{ counter }}
            <button @click="increment()" class="bg-blue-200 rounded items-center px-2 w-6">
                +
            </button>

        </div>
    </div>
</template>