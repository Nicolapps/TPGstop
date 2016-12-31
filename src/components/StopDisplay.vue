<template>
  <section>
    <div class="container-fluid">
      <div class="row">
        <div class="col-xs-8 col-xs-offset-2">
          <header>
            <div>
              <div class="company"></div>
              <h2>{{ stop.name }}</h2>
            </div>
            <span class="onDemand" v-if="stop.onDemand">Arrêt sur demande</span>
          </header>
          <ul class="lines">
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'StopResult',
  props: ['stop'],
};
</script>

<style scoped>
section {
  background: linear-gradient(to bottom, #9be2fe 0%, #67d1fb 100%);

  padding: 5em 0;
}

header {
  margin-top: 40%;
}

header > div {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: #fff;
}

.onDemand {
  position: absolute;
  bottom: 0;
  
  margin: 1%;
  
  font-size: 3vw;
}

.company {
  background: #f60;
  height: 30%;
}

h2 {
  font-size: 6.5vw;
  letter-spacing: .01em;
  margin: 1% 2.5%;
  padding: .2%;
  line-height: 1.2;

  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}
</style>
