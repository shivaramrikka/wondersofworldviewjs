<script setup>
import Image from './Image.vue';
defineProps(['wonderItem'])
</script>

<template>
    <div class="card">
        <h2>{{ wonderItem.name }}</h2>
        <div>
            <Image :image="wonderItem.image" />
            <p class="topic-paragraph">{{ wonderItem.description }}</p>
        </div>
    </div>
</template>

<style scoped>
.card {
  clear: both;
    overflow: visible;
    margin-bottom: 20px;
}
h2 {
  overflow: visible;
    margin-bottom: 30px;
    font-size:  1.5rem;
}
.topic-paragraph{
  font-size: 1.125rem;
    line-height: 1.6;
    word-wrap: break-word;
}

@media screen and (max-width:600px) {
  .card div {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}

</style>