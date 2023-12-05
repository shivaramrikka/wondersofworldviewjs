<script setup>
defineProps(['image'])
</script>
<template>
    <figure>
          <div>
            <img :src="image" alt="image">
          </div>
          <figcaption>
            Great Wall of China, near Beijing.
          </figcaption>
        </figure>
</template>
<style scoped>
figure {
  clear: right;
    float: right;
    margin-left: 20px;
    margin-bottom: 20px;
    width: 300px;
    /* margin: 0 0 1rem; */
}
figcaption{
  color: #666;
  font-size: 14px;
  margin-top: 5px;
}
img {
  width: 100%;
}
</style>