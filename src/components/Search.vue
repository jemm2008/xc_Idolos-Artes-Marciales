<template>
  <div class="d-flex justify-content-center">
    <div class="row mt-4">
      <div class="col-lg-12">
        <h4>Encuentra tu peleador por ID</h4>
      </div>
    </div>
    <br><br>
    <div class="row mt-3">
      <div class="col-lg-12">
        <form class="form-inline" @submit.prevent="findPeleador(id)">
          <div class="form-group mx-sm-3 mb-2">
            <input type="text" v-model="id" class="form-control" placeholder="Ingrese ID" />
          </div>
          <button type="submit" class="btn btn-primary mb-2">Buscar ahora!</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Search-view",
    data() {
      return {
        id: "",
      };
    },
    methods: {
      findPeleador(id) {
        this.$router.push(`/list/${id}`)
      },
    }
  }
</script>

<style>
</style>