<template>
    <section>
        <div
            :class="`side-bar ${sideBarMini ? 'w-14' : 'w-64'} h-screen bg-slate-100 rounded-xl text-slate-700 select-none shadow-2xl shadow-slate-100`">
            <header>
                <div class="flex items-center">
                    <button @click="toggleSidebar" class="w-auto h-12 p-3" href="">
                        <ion-icon :name=icon class="text-3xl"></ion-icon>
                    </button>
                    <a :class="`text-xl ${sideBarMini ? 'hidden' : 'md:block'}`" href="">{{ title }}</a>
                </div>
            </header>
            <main>
                <ItemsList title="Formulario" icon="help-outline" route="" :hide-title="sideBarMini"></ItemsList>
                <ItemsList title="Navbar" icon="arrow-forward-outline" route="" :hide-title="sideBarMini"></ItemsList>
            </main>
            <footer></footer>
        </div>
    </section>
</template>

<script setup>
import { defineProps, ref, defineEmits } from 'vue';
import ItemsList from './ItemsList.vue';

const emits = defineEmits(['changeIcon']);

const props = defineProps({
    title: {
        required: true,
        type: String,
    },
    icon: {
        required: false,
        type: String,
    }
});

const sideBarMini = ref(false);

const toggleSidebar = () => {
    sideBarMini.value = !sideBarMini.value;
    emits('change-icon', sideBarMini.value ? 'caret-forward-outline' : 'caret-back-outline');
};

</script>

