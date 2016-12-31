<template>
  <section>
    <div class="container">
      <h2>Lignes</h2>

      <div class="row">
        <div class="col-md-6" v-for="(line, index) in lines">
          <div class="panel panel-default">
            <div class="panel-body">
              <div class="row">
              
                <div class="col-sm-4">
                  <div class="form-group">
                    <label>N°</label>
                    <input class="form-control" type="text" maxlength="2" v-model="line.name">
                  </div>
                </div>
                
                <div class="col-sm-8">
                  <table>
                    <tr>
                      <th>Destinations</th>
                      <th>Terminus</th>
                    </tr>
                    <tr v-for="destination in line.destinations">
                      <td>
                        <input class="form-control" type="text">
                      </td>
                      <td>
                        <input type="checkbox" v-model="destination.terminus">
                      </td>
                    </tr>
                  </table>
                </div>
                
              </div>
              
              <button class="btn btn-danger" @click="removeLine(index)">Supprimer</button>
            </div>
          </div>
        </div>
      </div>
      
      <button class="btn btn-lg btn-success" @click="newLine"><span class="glyphicon glyphicon-plus-sign"></span> Ajouter</button>
      
    </div>
  </section>
</template>

<script>
export default {
  name: 'LinesSettings',
  props: ['lines'],
  methods: {
    newLine() {
      this.lines.push({
        name: '',
        destinations: [
          { name: '', terminus: false },
          { name: '', terminus: false },
          { name: '', terminus: false },
          { name: '', terminus: true },
        ],
      });
    },
    removeLine(index) {
      this.lines.splice(index, 1);
    },
  },
};
</script>

<style scoped>
section {
  padding: 3em 0;
}

table {
  width: 100%;
}

th, td {
  padding: 5px;
}

input[type="checkbox"] {
  display: block;
  margin: 0 auto;
}
</style>
