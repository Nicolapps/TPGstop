<template>
  <div id="app">
    <page-header></page-header>
    <stop-settings :stop.sync="stop"></stop-settings>
    <lines-settings></lines-settings>
    <stop-display :stop="stop"></stop-display>
  </div>
</template>

<script>
import PageHeader from 'components/PageHeader';
import LinesSettings from 'components/LinesSettings';
import StopSettings from 'components/StopSettings';
import StopDisplay from 'components/StopDisplay';

export default {
  data() {
    return {
      stop: {
        name: 'Bel-Air',
        onDemand: false,
      },
    };
  },
  name: 'app',
  components: { PageHeader, LinesSettings, StopSettings, StopDisplay },
};
</script>

<style>
body {
  border-top: 10px solid #F38630;
}
</style>
