
<template>
  <span class="LinePictogram" :style="style">
    {{ line }}
  </span>
</template>

<script>
import lineColors from './lineColors';

export default {
  name: 'LinePictogram',
  props: ['line'],

  computed: {
    style() {
      if (!(this.line in lineColors)) { // Ligne inconnue
        return {
          border: '1px solid black',
          color: 'black',
        };
      }

      return {
        color: lineColors[this.line].text,
        'background-color': lineColors[this.line].back,
      };
    },
  },
};
</script>

<style scoped>
.LinePictogram {
  display: block;
  height: 1.45em;
  width: 2em;

  border-radius: 9999px;

  font-family: 'Helvetica Neue', 'Helvetica', 'Roboto', sans-serif;
  font-weight: bold;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
