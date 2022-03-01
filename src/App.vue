<template>
  <div
    class="flex"
  >
  <div
    class="w-1/2 h-screen"
    :style="{ background: `hsl(${picked.h}, ${picked.s}%, ${picked.l}%)`}"
  ></div>
  <div class="w-1/2 flex flex-col justify-around">
    <hue-picker
      :picked="picked"
      :setHue="setHue"
    ></hue-picker>
    <saturation-picker
      :picked="picked"
      :setSaturation="setSaturation"
    ></saturation-picker>
    <lightness-picker
      :picked="picked"
      :setLightness="setLightness"
    ></lightness-picker>
  </div>
  </div>
</template>

<script>
import HuePicker from './components/HuePicker';
import SaturationPicker from './components/SaturationPicker';
import LightnessPicker from './components/LightnessPicker';

export default {
  name: 'App',
  components: {
    HuePicker,
    SaturationPicker,
    LightnessPicker,
  },
  data () {
    return {
      picked: {
        h: 200,
        s: 80,
        l: 50,
      },
    };
  },
  methods: {
    setHue (hue) {
      this.picked.h = hue;
    },
    setSaturation (sat) {
      this.picked.s = sat;
    },
    setLightness (lig) {
      this.picked.l = lig;
    },
  }
}
</script>
