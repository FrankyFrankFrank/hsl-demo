<template>
  <div class="flex justify-between">
    <div
      v-for="lig in lightnesses"
      class="h-8 w-8 flex-grow"
      :style="{ background: `hsl(${picked.h}, ${picked.s}%, ${lig}%)`}"
      @click="setLightness(lig)"
    >
    </div>
  </div>
</template>

<script>
export default {
  name: 'lightness-picker',
  props: [
    'picked',
    'setLightness',
  ],
  computed: {
    lightnesses() {
      let lightnesses = []
      for (let i = 0; i <= 100; i += 10) {
        lightnesses.push(i)
      }
      return lightnesses
    }
  }
}
</script>