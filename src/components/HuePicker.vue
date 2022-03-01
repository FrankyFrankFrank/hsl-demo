<template>
  <div class="flex">
    <div
      v-for="hue in hues"
      class="h-8 w-8 flex-grow"
      :style="{ background: `hsl(${hue}, ${picked.s}%, ${picked.l}%)`}"
      @click="setHue(hue)"
    >
    </div>
  </div>
</template>

<script>
export default {
  name: 'hue-picker',
  props: [
    'picked',
    'setHue',
  ],
  computed: {
    hues() {
      let hues = []
      for (let i = 0; i <= 360; i += 10) {
        hues.push(i)
      }
      return hues
    }
  }
}
</script>