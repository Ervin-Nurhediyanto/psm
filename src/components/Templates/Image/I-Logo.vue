<template>
  <div class="d-flex justify-content-center shadow-sm bg-body rounded">
    <div class="h-25 w-25">
      <img v-bind:src="image" alt="Logo" class="h-100 w-100"/>
    </div>
  </div>
</template>

<script>
import image from '../../../assets/Gear.gif'

export default {
  name: 'Image-Logo',
  data () {
    return {
      image: image
    }
  }
}
</script>
