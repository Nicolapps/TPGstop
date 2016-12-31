<template>
  <section>
    <div class="container">
      <h2>Arrêt</h2>

      <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label for="name">Nom de l'arrêt</label>
            <input class="form-control" type="text" v-model="stop.name" id="name">
          </div>
          <div class="form-group">
            <label>
              <input type="checkbox" v-model="stop.onDemand"> Arrêt sur demande
            </label>
          </div>
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
  background: #f3f3f3;
  padding: 3em 0;
}
</style>
