<script setup>
import { ref, onMounted } from 'vue';
import WondersList from './components/WondersList.vue';
import Navbar from './components/Navbar.vue';
const data = ref([])
onMounted(() => {
  fetch('https://wondersofworld.onrender.com/api')
    .then(response => response.json())
    .then(res => data.value = res)
})
</script>

<template>
  <div>
  <header>
    <Navbar />
  </header>
  <main>
    <template v-if="!(data && data.length > 0)">
        <h1>Loading data ....!</h1>
      </template>
      <template v-if="data && data.length > 0">
        <WondersList :items="data" />
      </template>

  </main>
  <footer>
      <section class="contact-links">
                      <ul>
                          <li class="nav-item">
                            <a class="nav-link" target="_blank" href="https://www.linkedin.com"><img
                                      width="10" height="10" class="icon"
                                      src="https://cdn-icons-png.flaticon.com/256/174/174857.png" />
                            </a>
                          </li>
                          <li class="nav-item"><a class="nav-link" target="_blank" href="https://www.facebook.com"><img
                                      width="10" height="10" class="icon"
                                      src="https://cdn-icons-png.flaticon.com/512/1312/1312139.png" />
                                  </a></li>
                          <li class="nav-item"><a class="nav-link" target="_blank" href="https://www.twitter.com"><img
                                      width="10" height="10" class="icon"
                                      src="https://cdn-icons-png.flaticon.com/256/124/124021.png" /> </a>
                          </li>
                          <li class="nav-item"><a class="nav-link" target="_blank" href="https://www.instagram.com"><img
                                      width="10" height="10" class="icon"
                                      src="https://cdn-icons-png.flaticon.com/512/3955/3955024.png" />
                                  </a></li>
                      </ul>
                  </section>
  </footer>
    </div>
</template>

<style scoped>
header, footer {
  color: #fff;
  left: 0;
  position: sticky;
  right: 0;
  top: -1px;
  transform: translateZ(0);
  z-index: 1061;
  background-color: #071c2e;
  height: 65px;
  position: relative;
  border: 5px solid rgba(0, 0, 0, 0);
  display: flex;
  justify-content: center;
  align-items: center;
}
main{
  width: 75%;
    margin: 1rem auto;
}

.contact-links ul{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

.contact-links ul li a {
    font-size: 14px;
}
.contact-links ul li {
    display: flex;
    align-items: center;
    margin: 0 20px;
}
.icon {
  width: 20px;
    height: 20px;
}
h1 {
  text-align: center;
}

@media screen and (max-width:600px) {
  header {
    height: unset;
  }
}
</style>
