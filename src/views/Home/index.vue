<template>
  <div class="col-12 h-100vh bg-info">
    <Navbar/>
    <router-view />
  </div>
</template>

<script>
import Navbar from '../../components/Navbar/navbar.vue'

export default {
  name: 'Home',
  components: {
    Navbar
  }
}
</script>
