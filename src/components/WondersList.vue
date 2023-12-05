<script setup>
import WonderItem from './WonderItem.vue';
defineProps(['items'])
</script>
<template>
    <div v-for="item in items" :id="item.name">
        <WonderItem :wonderItem="item" />
    </div>
</template>