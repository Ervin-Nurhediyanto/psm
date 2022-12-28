<template>
  <div class="d-flex justify-content-center shadow-sm rounded bg-white">
    <div class="h-50 w-50">
      <img v-bind:src="image" alt="Logo" class="h-100 w-100"/>
    </div>
  </div>
</template>

<script>
import image from '../../../assets/logo.png'

export default {
  name: 'Image-Logo',
  data () {
    return {
      image: image
    }
  }
}
</script>
