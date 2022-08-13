<template>
  <div class="contenedor">
    <div v-if="peleador">
      <h1 class="mt-4 text-center fw-bold">¡Peleador encontrado!</h1>
      <div class="card mt-3 mb-4" style="max-width: 540px;">
        <div class="row g-0">
          <div class="col-md-5">
            <img :src="peleador.imgSrc" class="img-fluid rounded-start peleador" alt="...">
          </div>
          <div class="col-md-7">
            <div class="card-body">
              <h5 class="card-title">{{ peleador.nombre }}</h5>
              <p class="card-text">{{ peleador.texto }}</p>
              <hr>
              <p class="card-text"><small class="text-muted">ID Peleador: {{ peleador.id }}</small></p>
            </div>
          </div>
        </div>
      </div>
      <router-link to="/search" class="btn btn-sm btn-warning text-center">Volver a buscar</router-link>
    </div>
    <div v-if="!peleador">
      <h1>K.O</h1>
      <img src="../assets/img/404.jpg">
      <h3>La página que buscas no existe</h3>
      <div class="row mt-4 d-flex justify-content-center">
        <router-link to="/search" class="btn btn-sm btn-danger text-center">Volver a buscar</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Results-view",
  data: () => ({
    peleador: ""
  }),
  created() {
    const idPeleador = this.$route.params.id
    fetch("/peleadores.json")
      .then((res) => res.json())
      .then((data) => {
        this.peleador = data.find((item) => (
          item.id == idPeleador
        ));
      });
  },
}
</script>
<style scoped>
.peleador {
  height: auto;
  background-position: center;
  background-repeat: no-repeat;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

.contenedor{
  display: flex;
  justify-content: center;
}
</style>