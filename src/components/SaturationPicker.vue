<template>
  <div class="flex justify-between">
    <div
      v-for="sat in saturations"
      class="h-8 w-8 flex-grow"
      :style="{ background: `hsl(${picked.h}, ${sat}%, ${picked.l}%)`}"
      @click="setSaturation(sat)"
    >
    </div>
  </div>
</template>

<script>
export default {
  name: 'saturation-picker',
  props: [
    'picked',
    'setSaturation',
  ],
  computed: {
    saturations() {
      let saturations = []
      for (let i = 0; i <= 100; i += 10) {
        saturations.push(i)
      }
      return saturations
    }
  }
}
</script>