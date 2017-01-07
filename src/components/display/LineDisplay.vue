<template>
  <li>
    <div class="pictogram">
      <line-pictogram :line="line.name"></line-pictogram>
    </div>
    <ul :style="{ color: color }" class="destinations">
      <li v-for="destination in line.destinations">
        <span :class="{ terminus: destination.terminus }">
          <span class="destination">{{ destination.name }}</span>
        </span>
      </li>
    </ul>
  </li>
</template>

<script>
import LinePictogram from './LinePictogram';
import lineColors from './lineColors';

export default {
  name: 'LineDisplay',
  props: ['line'],
  components: { LinePictogram },
  computed: {
    color() {
      if (!(this.line.name in lineColors)) { // Ligne inconnue
        return '#333';
      }

      return lineColors[this.line.name].back;
    },
  },
};
</script>

<style scoped>
.lines li {
  display: flex;
  background: #fff;
  padding: 3%;
  margin-top: 2%;
}

.pictogram {
  font-size: 6.7vw;
}

.destinations {
  margin-top: -0.5%;
  padding-left: 0;
  list-style-type: none;
  flex: 1;
}

.destinations li {
  padding: 0;
  margin: 0;
  padding-left: 6%;
  height: 2.65vw;

  overflow: hidden;

  font-size: 2.2vw;
  line-height: normal;
}

.destination {
  color: #333;
}

.terminus {
  position: relative;
  left: -6%;

  font-weight: bold;
}

.terminus:before {
  content: '➜ ';
}
</style>
