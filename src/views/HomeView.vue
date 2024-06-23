<template>
<div>
    <button @click="openModal = true">Abrir</button>
    
    <Modal v-if="openModal" @close-modal="openModal = false">
        <template #default>
            <form action="" method="get">
                <input type="text" name="" placeholder="Email">
                <input type="text" name="" placeholder="Senha">
                <button>Login</button>
            </form>
        </template>
    </Modal>
</div>
</template>

<script setup>

import {ref} from 'vue';
import Modal from '@/components/Modal.vue'

const openModal = ref(false);
</script>

