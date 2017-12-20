<template>
  <div id="app">
    <page-header></page-header>
    <stop-settings :stop.sync="stop"></stop-settings>
    <lines-settings :lines.sync="lines"></lines-settings>
    <display-section :stop="stop" :lines="lines"></display-section>
  </div>
</template>

<script>
import PageHeader from 'components/PageHeader';
import LinesSettings from 'components/LinesSettings';
import StopSettings from 'components/StopSettings';
import DisplaySection from 'components/display/DisplaySection';

export default {
  data() {
    return {
      stop: {
        name: 'Bachet-de-Pesay',
        onDemand: false,
      },
      lines: [
        {
          name: '12',
          destinations: [
            { name: 'Plainpalais', terminus: false },
            { name: 'Bel-Air', terminus: false },
            { name: 'Rive', terminus: false },
            { name: 'Moillesulaz', terminus: true },
          ],
        },
      ],
    };
  },
  name: 'app',
  components: { PageHeader, LinesSettings, StopSettings, DisplaySection },
};
</script>

<style>
body {
  border-top: 10px solid #F38630;
}
</style>
