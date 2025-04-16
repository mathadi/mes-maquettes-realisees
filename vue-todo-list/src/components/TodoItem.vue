<script setup>
import {ref} from 'vue';
    defineProps({
        to_do: Object
    })

    const editing = ref(false);
    const editText = ref("");

    function startEdit(to_do){
        editing.value = true;
        editText.value = to_do.title;
    }

</script>

<template>
    <li :class="{c_editing: editing}">
        <div class="view">
            <input type="checkbox" class="toggle">
            <label @dblclick="startEdit(to_do)">{{ to_do.title }}</label>
            <button class="destroy" aria-label="Supprimer"></button>
        </div>
        <div class="edit-input">
            <input type="text" class="edit" v-model="editText">
            <label for="" class="hidden">Editer</label>
        </div>
    </li>
</template>

<style scoped>
    .hidden{
        display: none;
    }
</style>